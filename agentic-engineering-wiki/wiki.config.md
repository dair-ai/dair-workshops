# Wiki Config: AI Agent Engineering

## Identity

- **Slug:** `agentic-engineering`
- **Title:** AI Agent Engineering
- **Flavor:** domain (with organization + paper elements)
- **Created:** 2026-04-28

## Purpose

A living reference for developers building AI agents. Distills practical tips, patterns, and lessons from company engineering blogs, official docs, community discussions, research papers, and open-source tools into scannable, source-backed, immediately applicable advice.

## Audience

Developers actively building, deploying, or evaluating AI agents. Assumes familiarity with LLMs, APIs, and basic agent concepts. Content should be specific enough for practitioners but not require deep research backgrounds.

## Content Principles

1. **Actionable over academic.** Every entry should answer "what do I do with this?"
2. **Source-grounded.** Every tip links back to a specific company blog post, doc page, Reddit thread, paper, or repo.
3. **Scannable.** Pages are designed to be skimmed — consistent tip format, clear headings, short paragraphs.
4. **Honest about uncertainty.** Mark speculation, opinion, and unverified claims explicitly.
5. **Temporal awareness.** Note when tips may be version-specific or time-bound.

---

## Page Types

### Primary: Tips (`wiki/tips/`)

The core content format. Each tip file covers one category of agent engineering.

**Current categories:**
- `tool-use.md` — Tool calling, MCP, function calling, tool selection
- `evaluation.md` — Evals, benchmarks, testing strategies, LLM-as-judge
- `prompting.md` — System prompts, instruction design, few-shot patterns
- `orchestration.md` — Multi-agent coordination, routing, delegation, workflows
- `memory.md` — Context management, RAG, state persistence, conversation history
- `reliability.md` — Guardrails, retries, fallbacks, error handling, safety
- `deployment.md` — Production, monitoring, observability, cost optimization

**Tip format template:**
```markdown
### Tip: [One-line actionable summary]

- **Source:** [Title](URL) — [Company / Reddit / HN / arxiv / GitHub]
- **Date added:** YYYY-MM-DD
- **Context:** [When does this apply? solo agent? multi-agent? production? prototyping?]
- **Difficulty:** beginner | intermediate | advanced

[2-4 sentence explanation of what the tip is and why it works.]

> Key insight: "..." (optional, direct quote from source)
```

**Adding new categories:** Create a new `.md` file in `wiki/tips/`, add it to the index below, and follow the tip format above. No other changes needed — the wiki is designed to grow organically.

---

### Company Pages (`wiki/companies/`)

One page per company tracking their agent-related publications, docs, and engineering content.

**Current companies:**
- `anthropic.md`
- `openai.md`
- `google-deepmind.md`
- `meta-ai.md`
- `stripe.md`
- `modal-ai.md`
- `deepseek.md`
- `mistral.md`
- `cohere.md`

**Company page template:**
```markdown
# [Company Name]

- **Last updated:** YYYY-MM-DD
- **Key resources:** [main docs URL], [engineering blog URL], [research blog URL]

## Recent Publications

| Date | Title | Type | Key Takeaway |
|------|-------|------|--------------|
| ... | ... | blog/doc/paper | One-line summary |

## Recurring Themes

[What patterns show up repeatedly in their content?]

## Agent-Specific Resources

[Links to their most relevant docs, cookbooks, SDKs for agent builders]
```

**Adding new companies:** Create a new `.md` file in `wiki/companies/` following the template, add to the index, and add their key resource URLs.

---

### Paper Pages (`wiki/papers/`)

Summaries of key arxiv papers relevant to agent engineering, focusing on practical takeaways.

**Paper page template (in-file):**
```markdown
### [Paper Title]

- **arxiv:** [URL]
- **Date:** YYYY-MM-DD
- **Authors:** [Lab / Institution]
- **Category:** [cs.AI / cs.CL / cs.LG]

**What:** [1-2 sentence summary]

**Key finding:** [Headline result with numbers]

**Practical takeaway:** [What should a builder do differently after reading this?]

**Limitations / caveats:** [Honest assessment]
```

---

### Tools (`wiki/tools/`)

Notable repos and tools from GitHub trending and other sources.

**Tool entry template:**
```markdown
### [Tool Name]

- **Repo:** [URL]
- **Date added:** YYYY-MM-DD
- **Category:** framework | eval | MCP | orchestration | memory | deployment | other

**What it does:** [1-2 sentences]

**Why it matters for agent builders:** [Practical significance]

**Maturity:** experimental | active development | production-ready
```

---

### Community (`wiki/community/`)

Highlights from Reddit and HackerNews discussions, preserving the conversational context.

- `reddit-highlights.md` — Notable threads from r/MachineLearning, r/LocalLLaMA, r/OpenAI, etc.
- `hn-highlights.md` — Notable agent-related HN threads and discussions

**Community entry template:**
```markdown
### [Thread Title]

- **Source:** [Reddit / HN URL]
- **Date added:** YYYY-MM-DD
- **Subreddit / context:** [if Reddit]

**The discussion:** [2-3 sentence summary of what was debated]

**Consensus / key takes:**

- Take 1
- Take 2

**Contrarian / minority view:** [if notable]
```

---

### Timeline (`wiki/timeline.md`)

Chronological log of major developments: model releases, framework launches, significant papers, company strategy shifts relevant to agent building.

---

## Source Architecture

| Source Type | Sources | What We Extract | Update Method |
|-------------|---------|-----------------|---------------|
| Company blogs/docs | Anthropic, OpenAI, Meta AI, Google DeepMind, Stripe, Modal AI, DeepSeek, Mistral, Cohere | Engineering posts, docs updates, cookbooks, case studies | Manual + automation |
| Community | Reddit (r/ML, r/LocalLLaMA, r/OpenAI, r/ClaudeAI), HackerNews | Discussions, war stories, critiques | Automation (daily) |
| Research | arxiv (cs.AI, cs.CL, cs.LG) | New agent architectures, evals, benchmarks | Automation (daily) |
| Tools | GitHub trending | Agent frameworks, MCP servers, eval tools | Automation (daily) |

**Adding new source types:** Add a row to this table, create a folder under `wiki/` if needed, and add the collection method.

---

## Update Workflow

1. **Pull** — Fetch new content from sources
2. **Store** — Save raw content in `raw/` with provenance
3. **Distill** — Extract actionable tips into `wiki/tips/<category>.md`
4. **Track** — Update company pages with new publications
5. **Index** — Refresh `wiki/index.md` with latest highlights
6. **Log** — Record updates in `logs/maintenance-log.md`

---

## Future-Proofing

This wiki is designed for extensibility. The following can be added at any time without restructuring:

- **New tip categories** — Create a new `.md` in `wiki/tips/`, add to index
- **New companies** — Create a new `.md` in `wiki/companies/`, add key URLs
- **New source types** — Create folder under `wiki/`, add template to this config
- **New content formats** — Add a folder (e.g., `wiki/patterns/`, `wiki/playbooks/`, `wiki/anti-patterns/`) with its own template
- **Sub-categories** — Split an existing tip file into multiple files (e.g., `tool-use.md` → `tool-use-selection.md` + `tool-use-mcp.md`)

The index page (`wiki/index.md`) is the single place that needs updating when structure changes.