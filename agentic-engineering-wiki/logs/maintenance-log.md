# Maintenance Log

Record of major actions on the AI Agent Engineering wiki.

---

## 2026-04-28 — Initial Scaffolding

- Created wiki with `init_wiki.sh agent-engineering --title "AI Agent Engineering" --flavor domain` (renamed to `agentic-engineering-wiki` on 2026-04-29)
- Established directory structure: `tips/`, `companies/`, `papers/`, `tools/`, `community/`
- Wrote `wiki.config.md` with full templates, flexibility guidelines, and future-proofing notes
- Created 7 tip category pages: tool-use, evaluation, prompting, orchestration, memory, reliability, deployment
- Created 9 company pages: Anthropic, OpenAI, Google DeepMind, Meta AI, Stripe, Modal AI, DeepSeek, Mistral, Cohere
- Created community pages: reddit-highlights, hn-highlights
- Created papers index and tools index
- Created timeline and sources registry
- **Status:** Scaffolded, ready for first content ingestion

---

## 2026-04-28 — First Content Ingestion

- Fetched Anthropic tool use docs (overview + how-tool-use-works + agents-and-tools)
- Fetched OpenAI Agents SDK guide (platform docs)
- Fetched Google Gemini Agents Overview + Prompting Strategies
- Saved raw extracts to `raw/2026-04-28/`
- Compiled 15 tips across 5 categories:
  - **Tool Use (5):** strict mode, tool type differentiation, regex→tool call, agentic loop, tool leverage
  - **Prompting (2):** Google agentic system instruction template, OpenAI surface selection
  - **Orchestration (2):** specialist handoffs, ADK framework choice
  - **Reliability (3):** guardrails before risky ops, persistence/risk/planning prompts, pause_turn handling
  - **Deployment (3):** sandbox agents, deployment surface selection, tool-level cost tracking
- Updated company pages: Anthropic (3 pubs), OpenAI (4 pubs), Google DeepMind (3 pubs)
- Updated index with latest tips table
- Updated sources.md with specific fetched URLs
- Updated timeline
- **Status:** 15 tips live, 3/9 companies populated, 5/7 categories populated

---

## 2026-04-28 — Second Content Ingestion

- Fetched Stripe Agent Toolkit docs, Cohere Tool Use docs, DeepSeek Function Calling guide, Mistral Agents docs, Modal blog (3 posts), Meta AI blog
- Searched Reddit (r/LocalLLaMA) and HackerNews for agent-building discussions
- Saved raw extracts to `raw/2026-04-28/` (6 new files, 9 total)
- Compiled 13 additional tips:
  - **Tool Use (3):** schema iteration as prompt engineering, multi-step tool use, Unix commands vs function calling
  - **Orchestration (2):** Mistral handoffs for state transfer, built-in connector tools
  - **Memory (3):** messages list as state ledger, persistent state across sessions, Modal Directory Snapshots
  - **Reliability (3):** restricted API keys (rk_*), tool_plan reasoning, sandbox testing for non-determinism
  - **Deployment (2):** elastic GPU access, multi-framework toolkit integration
- Updated all 9 company pages with publications
- Populated Reddit highlights (2 threads) and HN highlights (5 threads)
- Updated index, sources.md (20+ specific URLs), timeline
- **Status:** 40 tips, 9/9 companies, 7/7 categories, 10 papers, community populated. All source types (companies, Reddit, HN, arxiv) covered. Remaining: tools/repo entries.