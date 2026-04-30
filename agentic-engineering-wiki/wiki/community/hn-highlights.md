# HackerNews Highlights

Notable agent-related discussions from HackerNews.

**Last updated:** 2026-04-28

---

## Highlights

### Best Practices for Building Agentic AI Systems

- **Source:** [HN](https://news.ycombinator.com/item?id=44919647)
- **Date added:** 2026-04-28

**The discussion:** A solo developer shared practical lessons from building AI agents for UserJot, sparking extensive debate. Core advice: subagents as stateless functions, structured output as the key enabler, model tiering (cheaper models for 3/4 of tasks), and avoiding the "Smart Agent" trap.

**Key takes:**
- Subagents should be stateless functions — same input, same output, no shared memory, temp near 0
- Structured generation is the magic that makes agents work reliably
- Use cheaper/faster models for most tasks, reserve expensive ones for complex orchestration
- The "Smart Agent" trap: agents can't reliably figure out what to do — be explicit
- Context explosion is the hidden cost — don't pass entire conversation history to every agent

**Contrarian view:** Several commenters argue this describes deterministic workflows, not true agents. The distinction between "intelligent orchestration" and "agentic behavior" was a central debate.

### Ask HN: Best practices or example workflows for agentic development (March 2026)

- **Source:** [HN](https://news.ycombinator.com/item?id=47402366)
- **Date added:** 2026-04-28

**The discussion:** Practitioners sharing real-world agent development workflows and what actually works in production.

### The Hard Truth About AI Agents: What We Learned Building in Open Source

- **Source:** [HN](https://news.ycombinator.com/item?id=47208103)
- **Date added:** 2026-04-28

**Key takes:** Open-source agent builders sharing hard-won lessons about what works and what doesn't in practice.

### Building Effective AI Agents

- **Source:** [HN](https://news.ycombinator.com/item?id=44301809)
- **Date added:** 2026-04-28

**Key takes:** Discussion of Anthropic's "Building Effective Agents" guide and community reactions.

### What to build instead of AI agents

- **Source:** [HN](https://news.ycombinator.com/item?id=44450160)
- **Date added:** 2026-04-28

**The discussion:** Extended debate on when agents are the wrong tool. Key themes: context engineering is the hidden bottleneck, agents poison their own context over iterations, test suites as steering mechanisms, and the pragmatic view that deterministic problems don't need agents.

**Key takes:**
- Context management is MOST of the challenge — not the model
- Letting agents build their own context degrades quality (multiplicative reduction)
- Test suites are an extremely powerful reinforcement mechanism for agents
- If you can solve it algorithmically, do that — don't use an agent
- AI agents are "expensive temporary glue" — useful for exploring, then replaced by hard-coded functions
- Prompt engineering is "reverse-engineering a non-deterministic black box with unknown parameters"

---

## Related

- [Reddit Highlights](reddit-highlights.md)