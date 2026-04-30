# Deployment

Tips for deploying AI agents to production: monitoring, observability, cost optimization, and infrastructure.

**Last updated:** 2026-04-28

---

## Tips

### Tip: Use sandbox agents for container-based execution in production

- **Source:** [OpenAI Agents SDK — Sandbox Agents](https://platform.openai.com/docs/guides/agents/sandboxes) — OpenAI
- **Date added:** 2026-04-28
- **Context:** When your agent needs to run arbitrary code, install packages, or access files in a controlled environment
- **Difficulty:** intermediate

OpenAI's Python Agents SDK now supports sandbox agents: container-based environments with files, commands, packages, ports, snapshots, and memory. Use this when the agent needs to execute untrusted code, install dependencies on the fly, or maintain isolated state per session. Sandboxes provide the isolation guarantees of containers with the convenience of SDK integration. This is especially relevant for coding agents, data analysis agents, and any agent that needs to run arbitrary shell commands.

### Tip: Choose the right deployment surface: SDK vs hosted vs embedded

- **Source:** [OpenAI Agents SDK Guide](https://platform.openai.com/docs/guides/agents) — OpenAI
- **Date added:** 2026-04-28
- **Context:** When deciding how to deploy and serve an agent to users
- **Difficulty:** beginner

OpenAI offers three deployment surfaces with different trade-offs. The Agents SDK (TypeScript/Python) gives you full control over orchestration, tools, state, and infrastructure — best for custom backends and complex workflows. Agent Builder is the hosted visual editor + ChatKit path — best for rapid deployment with a managed UI. Direct client libraries are for simple model requests without agent orchestration. The decision tree: if you need typed code and full control → SDK; if you want hosted workflow creation and publishing → Agent Builder; if you need voice → SDK (Agent Builder doesn't support voice yet).

### Tip: Track agent costs at the tool-call granularity level

- **Source:** [Claude Tool Use Docs](https://docs.anthropic.com/en/docs/build-with-claude/tool-use/overview) — Anthropic
- **Date added:** 2026-04-28
- **Context:** Planning cost budgets for production agents
- **Difficulty:** intermediate

Anthropic bills tool use across three dimensions: input tokens (including the tools parameter with names, descriptions, and schemas), output tokens (including tool_use blocks), and per-use charges for server-side tools (web search charges per search, etc.). Client-side tools cost the same as any other API request. The system prompt for tool use adds approximately 346 tokens for most Claude models. When budgeting, account for: tool schema size in each request, tool_use and tool_result blocks in the agentic loop, and per-search/per-execution charges for server tools.

---

## Related

- [Evaluation](../evaluation.md) — Production evaluation and monitoring
- [Reliability](../reliability.md) — Production reliability patterns

---

### Tip: Give agents elastic GPU access for bursty workloads

- **Source:** [Modal — Autoscaling Autoresearch](https://modal.com/blog/autoscaling-autoresearch) — Modal AI
- **Date added:** 2026-04-28
- **Context:** Agents that sometimes need GPUs (code execution, model inference) but are idle most of the time
- **Difficulty:** advanced

Modal's autoscaling infrastructure lets agents request GPUs on demand and release them when done — no pre-provisioning, no idle costs. The pattern from their Autoresearch example: an agent spins up a GPU sandbox to run a model, gets results, and shuts it down. This is particularly relevant for agent architectures where the orchestrator runs on CPU but occasionally delegates to GPU-requiring sub-agents. Without elastic provisioning, you either over-pay for idle GPUs or under-provision and slow down agent execution.

### Tip: Integrate agent toolkits with your existing framework stack, not against it

- **Source:** [Stripe Agent Toolkit](https://docs.stripe.com/agents) — Stripe
- **Date added:** 2026-04-28
- **Context:** When choosing how to integrate third-party services into your agent
- **Difficulty:** beginner

Stripe's agent toolkit is a good reference: it ships with first-class support for OpenAI Agents SDK, Vercel AI SDK, LangChain, and CrewAI — in both Python and TypeScript — and works with any LLM provider that supports function calling. The lesson: when adding services to your agent (payments, search, databases), prefer toolkits that integrate with your existing framework rather than forcing you to adopt a new one. Check for multi-framework support before committing to a toolkit.