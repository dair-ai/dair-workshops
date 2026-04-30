# Agentic Engineering Wiki

A community-driven, living reference for developers building AI agents. 51 actionable tips, patterns, and lessons — distilled from company engineering blogs, research papers, Hacker News, Reddit, and open-source tools.

→ **[Browse the Wiki →](wiki/index.md)**

---

## What's Inside

| Section | Content |
|---------|---------|
| **Tips** (51) | Actionable advice: tool use, prompting, evaluation, reliability, memory, orchestration, deployment |
| **Companies** (9) | Agent-related docs & engineering content from Anthropic, OpenAI, Google, Meta, Stripe, and more |
| **Papers** (10) | Key research papers summarized for practitioners |
| **Tools** (14) | Notable open-source repos for agent development |
| **Community** | Curated highlights from HN and Reddit discussions |

---

## How to Use This Wiki

**If you're building your first agent:** Start with [Tool Use](wiki/tips/tool-use.md) (the agentic loop, tool schema design) and [Prompting](wiki/tips/prompting.md) (system prompt architecture, instruction hierarchy).

**If you're taking an agent to production:** Focus on [Evaluation](wiki/tips/evaluation.md) (trajectory-aware evals, repeat runs), [Reliability](wiki/tips/reliability.md) (guardrails, error handling), and [Deployment](wiki/tips/deployment.md) (cost tracking, sandbox execution).

**If you're researching or comparing approaches:** The [Companies](wiki/companies/) section tracks what each org is publishing, and the [Papers](wiki/papers/) section distills research into practical takeaways.

---

## Design Philosophy

- **Every claim links to a source.** No unsupported advice. Speculation is clearly marked.
- **Built for flexibility.** New categories, companies, and formats can be added at any time.
- **Community-first.** Pulled from real production experiences — HN threads, Reddit postmortems, company post-hoc writeups.

---

## Structure

```
agentic-engineering-wiki/
├── README.md              ← You are here
├── wiki/
│   ├── index.md           ← Main entry point
│   ├── tips/              ← 51 tips across 7 categories
│   ├── companies/         ← 9 company profiles
│   ├── papers/            ← 10 paper summaries
│   ├── tools/             ← 14 open-source tools
│   ├── community/         ← HN & Reddit highlights
│   └── timeline.md        ← Chronological developments
├── raw/                   ← Source material extracts
├── wiki.config.md         ← Templates & rules for maintainers
└── sources.md             ← Full provenance registry
```

---

## Contributing

This is a community resource. If you've learned something from building agents in production — a pattern, a failure mode, a counterintuitive result — open a PR or an issue.

See [wiki.config.md](wiki.config.md) for tip format templates and [sources.md](sources.md) for how to cite sources properly.

---

**Last updated:** 2026-04-29