# Memory

Tips for context management, RAG, state persistence, and conversation history in AI agents.

**Last updated:** 2026-04-28

---

## Tips

### Tip: Use the messages list as your agent's state ledger — not a black box

- **Source:** [Cohere Tool Use — State Management](https://docs.cohere.com/v2/docs/tool-use) — Cohere
- **Date added:** 2026-04-28
- **Context:** Any agent that makes tool calls and needs to track conversation context
- **Difficulty:** intermediate

Cohere's documentation provides a clear model for state management: the messages list is the explicit ledger. A single turn with tool calling consists of: user message → assistant message (with tool_plan + tool_calls) → tool message (with results) → final assistant message. Each step appends to the messages list, creating a complete, auditable trace. Key principle: don't hide state in a black-box session object — keep it in the messages list where both the model and your application can reason about it. This pattern applies universally: Anthropic's agentic loop and OpenAI's SDK use the same append-driven state model.

### Tip: Maintain persistent state across conversations for long-running agents

- **Source:** [Mistral Agents & Conversations API](https://docs.mistral.ai/capabilities/agents/) — Mistral
- **Date added:** 2026-04-28
- **Context:** User-facing agents that need memory across sessions (customer support, personal assistants, research agents)
- **Difficulty:** intermediate

Mistral's Conversations API explicitly supports persistent state across conversations. This means an agent can remember context from previous interactions — unlike stateless API calls where each session starts fresh. For production agents, persistent state is table stakes: users expect the agent to remember what was discussed. Implementation tip: store conversation summaries or key facts in a database, not the full message history. Inject relevant memories into the system prompt at session start rather than stuffing the entire history into context.

### Tip: Use Modal Directory Snapshots for resumable agent sandbox state

- **Source:** [Modal — Directory Snapshots](https://modal.com/blog/directory-snapshots-resumable-project-state-for-sandboxes) — Modal AI
- **Date added:** 2026-04-28
- **Context:** Coding agents or data analysis agents that need to pause, persist filesystem state, and resume later
- **Difficulty:** advanced

Modal's Directory Snapshots allow programmatic snapshotting of a directory within a running sandbox, then mounting it into another sandbox later — independently of the base image and the rest of the filesystem. For agents that do long-running work (coding, data processing), this means you can checkpoint filesystem state, shut down the sandbox (saving costs), and resume exactly where you left off in a new sandbox. Combined with sandbox agents (OpenAI) or Modal's own agent infrastructure, this enables cost-efficient, resumable agent execution.

---

### Tip: RAG is the wrong paradigm for agent memory — use hierarchical retrieval instead

- **Source:** [Beyond RAG for Agent Memory: Retrieval by Decoupling and Aggregation](https://arxiv.org/html/2602.02007v3) (xMemory) — arxiv
- **Date added:** 2026-04-28
- **Context:** Building persistent memory for agents with long conversation histories
- **Difficulty:** advanced

RAG targets large, heterogeneous corpora where retrieved passages are diverse and the failure mode is irrelevance. Agent memory is the opposite: a bounded, coherent dialogue stream where spans are highly correlated and often near-duplicates. Fixed top-k similarity retrieval collapses into one dense region, returning redundant evidence. The fix (from xMemory): disentangle memories into semantic components, organize them into a hierarchy, and retrieve top-down — selecting compact, diverse themes rather than similar-ranked chunks. This matters because most agent frameworks still default to flat RAG for memory, which is architecturally wrong for the use case.

### Tip: Agent memory is stateful persistence (write path), RAG is stateless (no write path) — use both

- **Source:** [AI Memory System vs RAG](https://atlan.com/know/ai-memory-system-vs-rag/) + [Memory for Autonomous LLM Agents](https://arxiv.org/html/2603.07670v1) — arxiv
- **Date added:** 2026-04-28
- **Context:** Architecting an agent that needs both real-time retrieval and cross-session memory
- **Difficulty:** intermediate

The 2026 practitioner consensus: RAG answers "what does the document say?" — stateless, no write path, resets every session. Agent memory answers "what has the agent learned?" — stateful, has a write path, accumulates across sessions. Most production agents need both working together. The memory survey identifies three generations: prompt-level compression (Gen 1), retrieval-augmented external stores/Gen 2, RAG, and end-to-end learned memory policies (Gen 3, like AgeMem which treats store/retrieve/update/summarize/discard as callable RL-optimized tools). Don't conflate the two — and don't skip the write path if your agent needs continuity.

### Tip: Context degradation is real and measurable — plan for it

- **Source:** [Lessons from Building AI Agents: Context Management](https://www.newtuple.com/post/lessons-from-building-ai-agents-context-management) + HN discussions
- **Date added:** 2026-04-28
- **Context:** Long-running agent sessions (coding agents, research agents, multi-turn chatbots)
- **Difficulty:** intermediate

Multiple independent sources confirm: model performance systematically drops as conversation length increases. Early interactions are sharp, but as the session grows, agents miss details, lose constraints, and contradict earlier decisions. This is "agent amnesia" — not a bug but a direct consequence of how context works. HN commenters observe: agents also poison their own context — letting agents build their own context over multiple iterations without manual curation degrades quality. Practical countermeasures: summarize and prune context at intervals, reset or fork sessions for new subtasks, and don't let agents self-modify their own system instructions without review.

- [Orchestration](../orchestration.md) — State management across agent handoffs
- [Deployment](../deployment.md) — Persistent memory in production