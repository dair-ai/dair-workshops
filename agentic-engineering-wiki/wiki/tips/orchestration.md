# Orchestration

Tips for multi-agent coordination, routing, delegation, and workflow design.

**Last updated:** 2026-04-28

---

## Tips

### Tip: Structure agents as specialists with explicit ownership via handoffs

- **Source:** [OpenAI Agents SDK — Orchestration and Handoffs](https://platform.openai.com/docs/guides/agents/orchestration) — OpenAI
- **Date added:** 2026-04-28
- **Context:** Building multi-agent systems where different agents handle different domains
- **Difficulty:** intermediate

Instead of one monolithic agent trying to handle everything, define individual specialists and use handoffs to transfer ownership. Each agent owns a specific domain and decides when to hand off to another specialist. The recommended reading order from OpenAI: start with a single agent definition, then add handoffs once ownership boundaries are clear. The framework handles the state transfer — your job is to define what each agent is responsible for and when it should delegate.

### Tip: Leverage Google's ADK for interoperable agent orchestration across frameworks

- **Source:** [Gemini Agents Overview](https://ai.google.dev/gemini-api/docs/agents) — Google DeepMind
- **Date added:** 2026-04-28
- **Context:** When building agents that need to work across different tool ecosystems and frameworks
- **Difficulty:** advanced

Google's Agent Development Kit (ADK) is an open-source framework specifically designed for building and orchestrating interoperable AI agents. It complements Gemini's built-in agent capabilities (Deep Research Agent) with a framework layer for custom orchestration. Gemini also integrates with LangChain/LangGraph (stateful graph-based flows), CrewAI (collaborative role-playing agents), LlamaIndex (RAG-enhanced workflows), and the Vercel AI SDK (frontend-focused agents). Choose based on your primary need: stateful graphs → LangGraph, collaborative teams → CrewAI, data-heavy → LlamaIndex, frontend → Vercel AI SDK.

---

### Tip: Use heterogeneous model teams — different models have different strengths

- **Source:** [Team of Thoughts: Efficient Test-time Scaling of Agentic Systems](https://arxiv.org/abs/2602.16485) — arxiv
- **Date added:** 2026-04-28
- **Context:** Multi-agent systems where you're choosing which models to use for which agents
- **Difficulty:** advanced

Team of Thoughts demonstrates that heterogeneous multi-agent systems (using different models for different roles) consistently outperform homogeneous ones. Their approach: (1) Orchestrator Calibration — identify which models have superior coordination and synthesis capabilities, and (2) Agent Self-Assessment — each agent profiles its own domain-specific strengths. The orchestrator dynamically activates the most compatible agents based on these profiles. Results: 96% on AIME24 vs 80% for homogeneous baselines. Practical takeaway: don't use the same model for every agent in a multi-agent system. Profile each model's strengths and match agents to tasks.

### Tip: Adopt the Plan-Execute-Verify-Replan loop for complex multi-agent workflows

- **Source:** [Verified Multi-Agent Orchestration (VMAO)](https://arxiv.org/pdf/2603.11445) — arxiv
- **Date added:** 2026-04-28
- **Context:** Complex queries that require coordination across multiple specialized agents
- **Difficulty:** advanced

VMAO introduces a verification-driven iterative loop for multi-agent systems: Plan (decompose into a DAG of sub-questions), Execute (parallel, with dependency-aware context propagation), Verify (an independent LLM evaluates whether results satisfy the original query), Replan (generate new sub-questions or retry incomplete ones). The key insight: verification at the orchestration level — not inside individual agents — provides a principled coordination signal. Combined with configurable stop conditions (completeness threshold, confidence, token budget, max iterations), this gives explicit quality-cost trade-offs.

- [Tool Use](../tool-use.md) — Tool calls are a form of delegation
- [Memory](../memory.md) — State management across agent handoffs

---

### Tip: Use handoffs for agent-to-agent delegation with state transfer

- **Source:** [Mistral Agents — Handoffs](https://docs.mistral.ai/capabilities/agents/) — Mistral
- **Date added:** 2026-04-28
- **Context:** Multi-agent workflows where different agents handle different phases of a task
- **Difficulty:** intermediate

Mistral's Agents and Conversations API provides built-in handoff capability, allowing agents to call other agents as part of a workflow. This enables patterns like: a planning agent hands off to an execution agent, or a generalist agent delegates to a specialist. The handoff mechanism preserves conversation state so the receiving agent has full context. Combined with Mistral's built-in connector tools (code execution, web search, image generation, document library), you can build sophisticated multi-agent workflows with minimal boilerplate.

### Tip: Use built-in connector tools to reduce tool scaffolding overhead

- **Source:** [Mistral Agents — Tools](https://docs.mistral.ai/capabilities/agents/) — Mistral
- **Date added:** 2026-04-28
- **Context:** When getting started with agents or prototyping rapidly
- **Difficulty:** beginner

Mistral provides built-in connector tools out of the box: code execution (sandboxed Python), web search, image generation, and document library (RAG over your documents with citations). These remove the need to build and host your own tool infrastructure for common agent capabilities. Even if you're not using Mistral, the pattern is worth adopting: pre-build reusable tool connectors for search, code execution, and retrieval rather than wiring them fresh for every agent.
---

### Tip: Represent agents as MCP servers — compose multi-agent systems over the same protocol

- **Source:** [Show HN: Representing Agents as MCP Servers](https://news.ycombinator.com/item?id=44053754) — HackerNews
- **Date added:** 2026-04-28
- **Context:** Building complex multi-agent systems that need to work across different clients
- **Difficulty:** advanced

The mcp-agent team demonstrated a paradigm shift: agents can be MCP servers themselves, exposing workflows as MCP tools. Any MCP-compatible client (Claude, Cursor, ChatGPT) can invoke, coordinate, and orchestrate agents the same way they do with any other MCP server. This enables agent composition over the same base protocol, platform independence, and the ability to run agent workflows on dedicated infrastructure. Combined with Temporal for durable execution, agents can pause, resume, and retry in production settings without losing state.
