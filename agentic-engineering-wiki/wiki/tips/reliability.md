# Reliability

Tips for guardrails, retries, fallbacks, error handling, and safety in AI agents.

**Last updated:** 2026-04-28

---

## Tips

### Tip: Add guardrails and human review before risky operations

- **Source:** [OpenAI Agents SDK — Guardrails and Human Review](https://platform.openai.com/docs/guides/agents/guardrails-approvals) — OpenAI
- **Date added:** 2026-04-28
- **Context:** Multi-step agents where some actions are irreversible or high-stakes (payments, deletions, external API calls with side effects)
- **Difficulty:** intermediate

OpenAI's Agents SDK provides built-in guardrail and approval patterns. The workflow: before an agent executes a risky action, the guardrail evaluates whether the operation should be allowed, blocked, or paused for human review. This is particularly important in production agents where automated decisions can have real consequences. Use this pattern when the workflow should block or pause before risky work continues, not as an afterthought.

### Tip: Encode persistence, risk assessment, and proactive planning in agent prompts

- **Source:** [Gemini Prompting Strategies — Agentic Workflows](https://ai.google.dev/gemini-api/docs/prompting-strategies#agentic-workflows) — Google DeepMind
- **Date added:** 2026-04-28
- **Context:** Any agent that executes multi-step workflows where errors can compound
- **Difficulty:** intermediate

Google's research shows that complex agents benefit from prompts that enforce three specific behaviors: persistence in the face of issues (don't give up, retry with adjustments), risk assessment (think about what could go wrong before executing), and proactive planning (anticipate what you'll need rather than reacting step by step). These behaviors improved agent reliability by approximately 5% across benchmarks. The key is being explicit: don't assume the model will naturally persist or assess risk — tell it to.

### Tip: Handle server tool pauses gracefully with `pause_turn`

- **Source:** [How Tool Use Works](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/how-tool-use-works) — Anthropic
- **Date added:** 2026-04-28
- **Context:** Agents using server-executed tools (web_search, code_execution, web_fetch) that may need multiple iterations
- **Difficulty:** intermediate

Server-executed tools run their own loop inside Anthropic's infrastructure, but there's an iteration limit. When the model hits the cap before finishing, the response comes back with `stop_reason: "pause_turn"` instead of `"end_turn"`. This means the work isn't finished — re-send the full conversation (including the paused response) to let the model continue where it left off. Ignoring `pause_turn` will silently truncate agent work.

---

### Tip: Watch for the "Lazy Agent" failure mode — the model knows it needs tools but doesn't call them

- **Source:** [ASA: Training-Free Representation Engineering for Tool-Calling Agents](https://arxiv.org/abs/2602.04935) — arxiv
- **Date added:** 2026-04-28
- **Context:** Agents that inconsistently use tools even when the situation clearly calls for them
- **Difficulty:** advanced

ASA identifies a critical "Lazy Agent" pattern: tool necessity is nearly perfectly decodable from mid-layer model activations, yet the model remains conservative about entering tool mode. This is a representation-behavior gap — the model knows it should use a tool but doesn't act on that knowledge. Their fix (Activation Steering Adapter) is a training-free, inference-time controller that amplifies true tool-use intent while suppressing spurious triggers, using only ~20KB of portable assets and no weight updates. Even if you don't implement ASA, knowing this failure mode exists changes how you debug: if the agent should have called a tool but didn't, don't just tweak the prompt — the intent may be there but suppressed.

### Tip: Don't use agents for problems with deterministic solutions — plain code still wins

- **Source:** [HN — What to Build Instead of AI Agents](https://news.ycombinator.com/item?id=44450160) — HackerNews
- **Date added:** 2026-04-28
- **Context:** Deciding whether to build an agent vs a traditional software solution
- **Difficulty:** beginner

A recurring theme across HN: "If you can solve the problem algorithmically you should definitely do that." ML practitioners with field experience are the most pragmatic about this. The heuristic: use agents when the solution space is not defined in advance (chat assistants, open-ended research, creative tasks) and the cost of being wrong is low. Use deterministic workflows when the process is well-understood, the cost of errors is high, or you need predictable behavior. AI agents are "expensive temporary glue" — useful for exploring a problem space and then being replaced by cheaper hard-coded functions once you understand it.

- [Evaluation](../evaluation.md) — Measuring reliability improvements
- [Tool Use](../tool-use.md) — Handling tool failures gracefully

---

### Tip: Use restricted API keys (rk_*) to limit agent blast radius

- **Source:** [Stripe Agent Toolkit](https://docs.stripe.com/agents) — Stripe
- **Date added:** 2026-04-28
- **Context:** Any production agent that accesses paid services, financial systems, or sensitive APIs
- **Difficulty:** intermediate

Stripe strongly recommends restricted API keys (rk_*) for agent integrations. These keys limit the agent's access to only the functionality it requires — tool availability is determined by the permissions you configure on the restricted key. This is critical because agent behavior is non-deterministic: you can't guarantee the agent won't attempt unauthorized operations. The general pattern: every production agent should operate with the minimum set of permissions needed, whether through restricted API keys, scoped IAM roles, or sandbox environments. A broad-scope key in an agent is an incident waiting to happen.

### Tip: Use tool_plan for explicit reasoning before acting

- **Source:** [Cohere Tool Use Docs](https://docs.cohere.com/v2/docs/tool-use) — Cohere
- **Date added:** 2026-04-28
- **Context:** High-stakes tool calls where you want the model to explain its reasoning before executing
- **Difficulty:** intermediate

Cohere's Chat endpoint returns a `tool_plan` field alongside `tool_calls` — the model's explicit reflection on what it should do next given the user query, before actually calling any tools. This is a built-in reliability checkpoint: you can inspect the plan before executing tool calls, or log it for auditing. Even if your provider doesn't expose `tool_plan` natively, you can replicate the pattern by requiring the model to output its plan before any tool call in your system prompt. The cost is latency (extra generation step); the benefit is debuggability and safety.

### Tip: Test agents in sandbox environments before production — non-determinism demands it

- **Source:** [Stripe Agent Toolkit](https://docs.stripe.com/agents) — Stripe
- **Date added:** 2026-04-28
- **Context:** Before deploying any agent that executes side effects (payments, writes, API calls)
- **Difficulty:** intermediate

Stripe explicitly calls out that agent behavior is non-deterministic and recommends using sandbox environments and running evaluations to assess performance. This applies universally: agents can and will behave differently across runs due to model temperature, context shifts, and tool interaction patterns. A production agent without sandbox testing is gambling. The workflow: develop against a sandbox/test environment with fake data → run eval suites against known test cases → only promote to production when evals pass consistently.