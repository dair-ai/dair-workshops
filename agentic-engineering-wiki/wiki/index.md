# AI Agent Engineering Wiki

A living reference for developers building AI agents. Tips, patterns, and lessons distilled from company engineering blogs, docs, community discussions, papers, and open-source tools.

**Last updated:** 2026-04-29 | **51 tips** | **7 categories** | **9 companies** | **10 papers** | **14 tools**

---

## Quick Start

Not sure where to begin? Here are three paths:

- 🛠️ **Building your first agent** → Start with [Tool Use](tips/tool-use.md) for the agentic loop and tool schema design, then [Prompting](tips/prompting.md) for system prompt architecture.
- 🚀 **Taking an agent to production** → [Evaluation](tips/evaluation.md) (trajectory-aware evals), [Reliability](tips/reliability.md) (guardrails, fallbacks), [Deployment](tips/deployment.md) (cost tracking, sandboxing).
- 🔬 **Researching or comparing approaches** → Browse [Companies](companies/) to see what each org publishes, and [Papers](papers/) for research distilled into practice.

---

## Browse by Category

| Category | Description |
|----------|-------------|
| [Tool Use](tips/tool-use.md) | Tool calling, MCP, function calling, tool selection (11 tips) |
| [Evaluation](tips/evaluation.md) | Evals, benchmarks, testing, LLM-as-judge (8 tips) |
| [Prompting](tips/prompting.md) | System prompts, instruction design, few-shot patterns (6 tips) |
| [Orchestration](tips/orchestration.md) | Multi-agent, routing, delegation, workflows (7 tips) |
| [Memory](tips/memory.md) | Context management, RAG, state, conversation history (6 tips) |
| [Reliability](tips/reliability.md) | Guardrails, retries, fallbacks, error handling (8 tips) |
| [Deployment](tips/deployment.md) | Production, monitoring, observability, cost (5 tips) |

---

## Latest Additions _(2026-04-28)_

- **Evaluation:** Trajectory-aware eval (not just final output), repeat runs for reliability, behavioral rubrics for LLM-as-judge, snapshot-based branching
- **Prompting:** Five-layer system prompt anatomy, tool descriptions as engineering surface, instruction hierarchy defense, multi-turn coherence loss
- **Tool Use:** Pre-filter tools to relevant subset per request, log agent intent to detect loops
- **Orchestration:** Agents as MCP servers for composable multi-agent systems

---

## Companies

Tracking agent-related publications, docs, and engineering content from key organizations:

| Company | Last Updated |
|---------|--------------|
| [Anthropic](companies/anthropic.md) | 2026-04-28 (3 publications) |
| [OpenAI](companies/openai.md) | 2026-04-28 (4 publications) |
| [Google DeepMind](companies/google-deepmind.md) | 2026-04-28 (3 publications) |
| [Meta AI](companies/meta-ai.md) | 2026-04-28 (2 publications) |
| [Stripe](companies/stripe.md) | 2026-04-28 (1 publication) |
| [Modal AI](companies/modal-ai.md) | 2026-04-28 (3 publications) |
| [DeepSeek](companies/deepseek.md) | 2026-04-28 (1 publication) |
| [Mistral](companies/mistral.md) | 2026-04-28 (1 publication) |
| [Cohere](companies/cohere.md) | 2026-04-28 (2 publications) |

---

## Research Papers

[Papers](papers/) — Key papers distilled into practical takeaways (10 papers)

---

## Tools & Repos

[Tools](tools/) — Notable agent-related repos from GitHub trending (14 tools)

---

## Community Pulse

| Source | Description |
|--------|-------------|
| [Reddit Highlights](community/reddit-highlights.md) | Notable threads (2 highlights) |
| [HN Highlights](community/hn-highlights.md) | Notable HN discussions (5 highlights) |

---

## Timeline

[Timeline](timeline.md) — Major developments in chronological order.

---

## About This Wiki

- **Purpose:** Practical, actionable advice for building AI agents — not academic surveys
- **Philosophy:** Every tip links to a source. No unsupported claims. Mark speculation clearly.
- **Design:** Built for flexibility. New categories, companies, sources, and formats can be added at any time.
- **Config:** See [wiki.config.md](../wiki.config.md) for templates and rules.
- **Sources:** See [sources.md](../sources.md) for full provenance registry.