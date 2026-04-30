# Tools & Repos

Notable repos, frameworks, and tools for building AI agents — surfaced from GitHub trending and other sources.

**Last updated:** 2026-04-28

---

## Agent Frameworks

### LangChain
- **Repo:** [langchain-ai/langchain](https://github.com/langchain-ai/langchain)
- **Date added:** 2026-04-28
- **Stars:** 134,892
- **Category:** framework

**What it does:** The most widely adopted agent engineering platform. Chains interoperable components, provides memory, tools, and model integrations. Includes Deep Agents (planning + subagents), LangGraph (graph-based orchestration), and LangSmith (evals + observability).

**Why it matters:** The ecosystem standard. Deep Agents adds file-system-based agent memory and subagent spawning. LangGraph enables stateful, controllable agent workflows with branching and human-in-the-loop.

**Maturity:** production-ready

---

### CrewAI
- **Repo:** [crewAIInc/crewAI](https://github.com/crewaiinc/crewAI)
- **Date added:** 2026-04-28
- **Stars:** 49,022
- **Category:** framework, orchestration

**What it does:** Lean, fast Python framework for multi-agent automation. Completely independent of LangChain. Provides Crews (collaborative intelligence) and Flows (enterprise event-driven architecture).

**Why it matters:** The go-to for role-playing multi-agent systems. Over 100,000 developers certified. CrewAI Flows enables granular, event-driven control for production deployments. Ships with AMP Suite for enterprise (tracing, control plane, SSO, on-prem).

**Maturity:** production-ready

---

### OpenAI Agents SDK (Python)
- **Repo:** [openai/openai-agents-python](https://github.com/openai/openai-agents-python)
- **Date added:** 2026-04-28
- **Stars:** 25,516
- **Category:** framework

**What it does:** Lightweight, provider-agnostic framework for multi-agent workflows. Supports 100+ LLMs. Features: agents with instructions/tools/guardrails, handoffs, agents-as-tools, realtime voice agents, sandbox agents.

**Why it matters:** The canonical SDK for OpenAI ecosystem. Provider-agnostic design means you're not locked to OpenAI models. Sandbox agents with container execution. Growing to 260+ contributors.

**Maturity:** production-ready

---

### DeerFlow (ByteDance)
- **Repo:** [bytedance/deer-flow](https://github.com/bytedance/deer-flow)
- **Date added:** 2026-04-28
- **Stars:** 25,000+
- **Category:** framework, multi-agent

**What it does:** ByteDance's open-source multi-agent framework. Hit #1 on GitHub Trending in February 2026.

**Why it matters:** Signals big tech investment in open-source agent frameworks. Rapid community adoption suggests practical utility.

**Maturity:** active development

---

## Memory Systems

### MemOS
- **Repo:** [MemTensor/MemOS](https://github.com/MemTensor/MemOS)
- **Date added:** 2026-04-28
- **Stars:** 8,447
- **Category:** memory

**What it does:** AI memory OS for LLM agents. Unifies store/retrieve/manage for long-term memory. +43.70% accuracy vs OpenAI Memory on benchmarks. Saves 35.24% memory tokens.

**Why it matters:** Top-tier memory benchmarks. 72% lower token usage vs loading full chat history. Multi-agent memory sharing. Both cloud and local (on-device) deployment options.

**Maturity:** production-ready

---

### MemMachine
- **Repo:** [MemMachine/MemMachine](https://github.com/MemMachine/MemMachine)
- **Date added:** 2026-04-28
- **Stars:** 3,521
- **Category:** memory

**What it does:** Open-source long-term memory layer. 5 lines of code to add persistent memory. Three memory types: episodic (graph-based conversation), profile (SQL facts/preferences), working (session context).

**Why it matters:** Minimal integration overhead. Memory survives restarts, sessions, and model changes. Growing contributor base (40+).

**Maturity:** active development

---

### Acontext
- **Repo:** [memodb-io/Acontext](https://github.com/memodb-io/Acontext)
- **Date added:** 2026-04-28
- **Stars:** 3,334
- **Category:** memory

**What it does:** Open-source skill memory layer. Automatically captures learnings from agent runs and stores them as agent skill files — readable, editable Markdown you can share across agents and frameworks.

**Why it matters:** Novel "Skill is Memory, Memory is Skill" philosophy. Plain files, no embeddings, no API lock-in. Progressive disclosure via tool use instead of semantic top-k. Export as ZIP, reuse anywhere.

**Maturity:** active development

---

### Ori Mnemos
- **Repo:** [aayoawoyemi/ori-mnemos](https://github.com/aayoawoyemi/ori-mnemos)
- **Date added:** 2026-04-28
- **Stars:** 247
- **Category:** memory

**What it does:** Local-first persistent memory with Recursive Memory Harness (RMH). Knowledge graph with ACT-R activation decay, spreading activation, Hebbian co-occurrence learning.

**Why it matters:** Benchmarks: 3.1× better recall than Mem0 on HotpotQA, 9.5× faster latency (120ms vs 1,140ms). Markdown + SQLite — no cloud dependency. Reinforcement learning on retrieval itself.

**Maturity:** experimental

---

## MCP & Developer Tools

### Serena
- **Repo:** [oraios/serena](https://github.com/oraios/serena)
- **Date added:** 2026-04-28
- **Stars:** 23,396
- **Category:** MCP, coding

**What it does:** Semantic IDE for coding agents via MCP. Provides symbol-level code retrieval, editing, refactoring, and debugging tools. Operates at the semantic level, not line numbers or regex.

**Why it matters:** Described as "the single most impactful addition" to Claude Code by users. Agent-first tool design — robust high-level abstractions. Integrates with any MCP-compatible client/LLM.

**Maturity:** production-ready

---

### CUA (Computer-Use Agents)
- **Repo:** [trycua/cua](https://github.com/trycua/cua)
- **Date added:** 2026-04-28
- **Stars:** trending
- **Category:** computer-use, sandbox

**What it does:** Open-source infrastructure for computer-use agents. Sandboxes, SDKs, and benchmarks to train and evaluate AI agents controlling full desktops (macOS, Linux, Windows).

**Why it matters:** Computer-use is the next frontier for agents — this provides the infrastructure layer. Desktop control with sandboxed safety boundaries.

**Maturity:** active development

---

### GenericAgent
- **Repo:** [lsdefine/GenericAgent](https://github.com/lsdefine/GenericAgent)
- **Date added:** 2026-04-28
- **Stars:** trending
- **Category:** framework

**What it does:** Self-evolving agent that grows a skill tree from a 3.3K-line seed, achieving full system control with 6x less token consumption.

**Why it matters:** Demonstrates the self-improving agent paradigm. Token efficiency gains are significant for production cost optimization.

**Maturity:** experimental

---

### context-mode
- **Repo:** [mksglu/context-mode](https://github.com/mksglu/context-mode)
- **Date added:** 2026-04-28
- **Stars:** trending
- **Category:** context, optimization

**What it does:** Context window optimization for AI coding agents. Sandboxes tool output, achieving 98% reduction in context usage. Supports 14 platforms.

**Why it matters:** Context is the #1 cost driver for agents. 98% reduction is a game-changing optimization for production deployments.

**Maturity:** active development

---

### Octopoda-OS
- **Repo:** [thomashillman/Octopoda-OS](https://github.com/thomashillman/Octopoda-OS)
- **Date added:** 2026-04-28
- **Stars:** —
- **Category:** memory, observability

**What it does:** Open-source memory operating system for AI agents. Persistent memory, semantic search, loop detection, agent messaging, crash recovery, real-time observability — all automatic.

**Why it matters:** Comprehensive memory + observability in one package. Loop detection catches agents burning tokens in repetitive patterns. Crash recovery with snapshot/restore. Agent-to-agent messaging.

**Maturity:** active development

---

## Observability & Evaluation

### promptfoo
- **Repo:** [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo)
- **Date added:** 2026-04-28
- **Stars:** trending
- **Category:** eval, security

**What it does:** Red teaming and pentesting for AI. CI/CD integration for enterprise security gaps in agent systems.

**Why it matters:** As agents deploy to production, security testing becomes critical. promptfoo addresses the gap between "does it work?" and "is it safe?"

**Maturity:** production-ready

---

### VoltAgent
- **Repo:** [VoltAgent/voltagent](https://github.com/voltagent/voltagent)
- **Date added:** 2026-04-28
- **Stars:** 8,406
- **Category:** framework, observability

**What it does:** End-to-end agent engineering platform. Open-source TypeScript framework (memory, RAG, guardrails, tools, MCP, voice, workflows) + VoltOps Console (observability, automation, deployment, evals).

**Why it matters:** Full-stack agent platform — code-level control + production operations. TypeScript-native. Growing fast (70+ contributors, 674 releases).

**Maturity:** production-ready

---

## Discovery Resources

### Awesome AI Agents 2026
- **Repo:** [caramaschiHG/awesome-ai-agents-2026](https://github.com/caramaschiHG/awesome-ai-agents-2026)
- **Date added:** 2026-04-28
- **Stars:** 451
- **Category:** discovery

**What it does:** 340+ tools across 20+ categories. Updated monthly. Covers coding agents, frameworks, browser/desktop agents, voice, creative, workflows, CRM, research, self-hosted, protocols, observability, safety.

**Why it matters:** The most comprehensive curated directory for discovering agent tools. Good starting point when exploring a new category.

---

## Related

- [Papers](../papers/) — Papers often come with released code
- [Companies](../companies/) — Company tools and SDKs