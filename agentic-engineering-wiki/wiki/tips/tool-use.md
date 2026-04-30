# Tool Use

Tips for tool calling, MCP integration, function calling, and tool selection in AI agents.

**Last updated:** 2026-04-28

---

## Tips

### Tip: Use `strict: true` to guarantee tool call schema conformance

- **Source:** [Claude Tool Use Docs](https://docs.anthropic.com/en/docs/build-with-claude/tool-use/overview) — Anthropic
- **Date added:** 2026-04-28
- **Context:** Any time your application logic depends on exact tool call shapes (production systems, typed languages, downstream consumers)
- **Difficulty:** beginner

Add `strict: true` to your tool definitions to ensure Claude's tool calls always match your schema exactly. Without it, the model may occasionally return arguments that don't conform to your schema, requiring defensive parsing. This is especially important in production systems where a malformed tool call can break downstream logic.

### Tip: Differentiate client tools, server tools, and Anthropic-schema tools

- **Source:** [How Tool Use Works](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/how-tool-use-works) — Anthropic
- **Date added:** 2026-04-28
- **Context:** Designing tool architecture for Claude-based agents
- **Difficulty:** intermediate

Tools fall into three buckets that determine who executes them. User-defined client tools run in your application; you handle the agentic loop. Anthropic-schema tools (bash, text_editor, computer, memory) also run client-side but use trained-in schemas that Claude calls more reliably. Server tools (web_search, code_execution, web_fetch, tool_search) run on Anthropic's infrastructure; you get results without handling execution. Prefer Anthropic-schema tools for bash and file editing since Claude recovers from errors more gracefully with them.

### Tip: If you're parsing model output with regex, it should be a tool call

- **Source:** [How Tool Use Works](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/how-tool-use-works) — Anthropic
- **Date added:** 2026-04-28
- **Context:** Any time you're post-processing model output to extract structured decisions
- **Difficulty:** beginner

The tell that you should be using tools: if you're writing a regex to extract a decision from model output, that decision should have been a tool call. Parsing free-form text to recover structured intent is a sign the structure belongs in the schema. Tool calls give you typed, guaranteed-shape outputs without fragile string parsing.

### Tip: Master the agentic loop pattern for client-side tools

- **Source:** [How Tool Use Works](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/how-tool-use-works) — Anthropic
- **Date added:** 2026-04-28
- **Context:** Any agent using client-side tools (user-defined or Anthropic-schema)
- **Difficulty:** intermediate

The canonical shape is a `while` loop keyed on `stop_reason`: send a request with tools, Claude responds with `stop_reason: "tool_use"` and `tool_use` blocks, execute each tool and format results as `tool_result` blocks, send a new request with the results, repeat. The loop exits on `"end_turn"`, `"max_tokens"`, `"stop_sequence"`, or `"refusal"`. For server tools, handle `"pause_turn"` by re-sending the conversation to let the model continue where it left off.

### Tip: Even basic tool access produces outsized capability gains

- **Source:** [Claude Tool Use Docs](https://docs.anthropic.com/en/docs/build-with-claude/tool-use/overview) — Anthropic
- **Date added:** 2026-04-28
- **Context:** When deciding whether to invest in tool infrastructure for an agent
- **Difficulty:** beginner

On benchmarks like LAB-Bench FigQA (scientific figure interpretation) and SWE-bench (real-world software engineering), adding even basic tools produces outsized capability gains, often surpassing human expert baselines. Tool access is one of the highest-leverage primitives you can give an agent. Don't over-engineer the toolset before you've tested with a few simple tools.

---

### Tip: Fine-tuned smaller models can beat frontier models on tool use with good data

- **Source:** [UniToolCall: Unifying Tool-Use Representation, Data, and Evaluation](https://arxiv.org/abs/2604.11557) — arxiv
- **Date added:** 2026-04-28
- **Context:** When cost or latency makes using frontier models impractical for every tool call
- **Difficulty:** advanced

UniToolCall fine-tuned Qwen3-8B on 390k tool-use instances and achieved 93.0% single-turn Strict Precision on distractor-heavy settings — outperforming GPT, Gemini, and Claude. The framework unifies tool-use representation into a Query-Action-Observation-Answer (QAOA) format and explicitly models single-hop vs multi-hop, single-turn vs multi-turn, and serial vs parallel execution structures. Practical takeaway: if tool-use reliability is critical and you're paying for frontier model calls, consider fine-tuning a smaller model on a well-structured tool-use corpus. The quality gap is smaller than assumed.

- [Orchestration](../orchestration.md) — Tool use often intersects with agent routing
- [Reliability](../reliability.md) — Handling tool failures and fallbacks

---

### Tip: Treat tool schema design as prompt engineering — iterate aggressively

- **Source:** [Cohere Tool Use Docs](https://docs.cohere.com/v2/docs/tool-use) — Cohere
- **Date added:** 2026-04-28
- **Context:** Any time you're defining tool schemas for an agent
- **Difficulty:** intermediate

Cohere explicitly recommends treating tool schema design like prompt engineering: the more descriptive and clear the schema (name, description, parameters), the more likely the LLM makes the right tool call decisions. Expect to iterate through several rounds on the `name`, `description`, and `properties` fields. A vague or underspecified tool schema leads to unreliable tool calls just like a vague prompt leads to unreliable outputs. This applies across all providers, not just Cohere — it's a universal principle of tool-calling systems.

### Tip: Leverage multi-step tool use for complex agentic reasoning

- **Source:** [Cohere Tool Use Usage Patterns](https://docs.cohere.com/v2/docs/tool-use) — Cohere
- **Date added:** 2026-04-28
- **Context:** When a single tool call round isn't enough — the agent needs to search, reason, then search again
- **Difficulty:** intermediate

Cohere's multi-step tool use pattern extends the basic tool loop: the model can decide to do a sequence of tool calls before generating its final response, running steps 2 (generate tool calls) and 3 (get tool results) multiple times. This enables agentic behaviors like: search for context → evaluate results → search with refined query → synthesize answer. The messages list accumulates tool_plan, tool_calls, and tool results across iterations, giving the model growing context to work with.

### Tip: Consider Unix-style command execution as an alternative to function calling

- **Source:** [r/LocalLLaMA — Ex-Manus Backend Lead on Function Calling](https://www.reddit.com/r/LocalLLaMA/comments/1rrisqn/i_was_backend_lead_at_manus_after_building_agents) — Reddit
- **Date added:** 2026-04-28
- **Context:** Especially relevant for local/self-hosted agents, but applicable broadly
- **Difficulty:** advanced

A former backend lead at Manus reported stopping function calling entirely after 2 years of building agents, replacing it with Unix-style command execution. Instead of defining function schemas and handling tool_result blocks, agents execute standard CLI commands and parse stdout. Benefits: simpler agent design, more robust error handling (Unix exit codes and stderr are well-understood), and reuse of existing CLI tools without writing wrapper functions. This is a counterintuitive but data-backed approach — worth considering if function calling complexity is costing more than it's giving.
---

### Tip: Pre-filter tools to a semantically relevant subset per request — 80 tools in context causes retry loops

- **Source:** [HN — How do you prevent MCP agents from looping in production?](https://news.ycombinator.com/item?id=47331249) — HackerNews
- **Date added:** 2026-04-28
- **Context:** Agents with large tool sets that experience looping or unnecessary tool calls
- **Difficulty:** intermediate

HN practitioners report that 80 tools in context causes the model to try irrelevant ones, fail, and retry — creating cascading loops. The fix: pre-filter to a semantically relevant subset per request. Simple BM25 on the incoming query against tool descriptions eliminates most retry loops before they start. Keep hard iteration caps as a backstop for genuinely pathological cases, not as your primary defense.

### Tip: Log agent intent at each step — same question in different syntax is a loop, not a retry

- **Source:** [HN — How do you prevent MCP agents from looping in production?](https://news.ycombinator.com/item?id=47331249) — HackerNews
- **Date added:** 2026-04-28
- **Context:** Debugging agent loops in production
- **Difficulty:** intermediate

Hard iteration limits don't tell you why the agent is looping. HN practitioners recommend logging the agent's intent at each step. If it's asking the same underlying question three times in different syntax, that's the signal to bail early — before burning through your iteration budget. Distinguish between: genuine retries (tool dependency flaky), confusion retries (agent doesn't understand the result), and planning loops (agent keeps re-deciding the same thing).
