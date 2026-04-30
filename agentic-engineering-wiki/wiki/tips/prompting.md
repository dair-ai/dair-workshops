# Prompting

Tips for system prompts, instruction design, few-shot patterns, and prompt engineering for agents.

**Last updated:** 2026-04-28

---

## Tips

### Tip: Use Google's agentic system instruction template to boost reliability

- **Source:** [Gemini Prompting Strategies — Agentic Workflows](https://ai.google.dev/gemini-api/docs/prompting-strategies#agentic-workflows) — Google DeepMind
- **Date added:** 2026-04-28
- **Context:** Multi-step agent workflows where reliability matters — especially tool calling, planning, and error recovery
- **Difficulty:** intermediate

Google found that a specific system instruction template improved agent performance by approximately 5% across several agentic benchmarks. The template explicitly instructs the model to persist through errors, assess risks before acting, plan proactively rather than reactively, and verify results after each tool call. Key behaviors to encode in your system prompt: don't give up on tool failures (retry with adjustments), think about what could go wrong before executing side effects, and always cross-check tool outputs against the original goal before declaring success.

> Key insight: "To maximize reliability in multi-step workflows, you should craft instructions that explicitly control how the model reasons and plans. Complex agents benefit from prompts that enforce specific behaviors like persistence in the face of issues, risk assessment, and proactive planning."

### Tip: Distinguish between the three prompt surfaces for OpenAI agents

- **Source:** [OpenAI Agents SDK Guide](https://platform.openai.com/docs/guides/agents) — OpenAI
- **Date added:** 2026-04-28
- **Context:** When choosing how to build an OpenAI-based agent
- **Difficulty:** beginner

OpenAI provides three distinct surfaces for building agents, and the prompt strategies differ. Use the Agents SDK when your server owns orchestration, tool execution, and state — this gives you full control over system prompts for each specialist agent. Use Agent Builder for the hosted visual workflow editor and ChatKit deployment. Use the direct client libraries for single-turn or simple multi-turn interactions. The SDK track is the right choice when you need typed application code, direct MCP server control, custom conversation strategies, and tight integration with existing infrastructure.

---

### Tip: Structure system prompts as a five-layer architecture, not a monologue

- **Source:** [Prompt Engineering for AI Agent Systems — Zylos Research](https://zylos.ai/research/2026-03-30-prompt-engineering-ai-agent-systems-instruction-hierarchies) + [Reverse-Engineering Claude Code's System Prompt](https://www.mynameisfeng.com/blog/the-complete-guide-to-writing-agent-system-prompts-lessons-from-reverse-engineering-claude-code)
- **Date added:** 2026-04-28
- **Context:** Designing system prompts for any agent, especially production ones
- **Difficulty:** intermediate

All major production agents (Claude Code, Cursor, Devin, Codex) converge on a five-layer anatomy: (1) identity framing — who the agent is, (2) behavioral rules — the operational constitution, (3) typed tool APIs — per-tool instructions beyond JSON schemas, (4) safety layers — woven throughout, not a separate block, (5) conditional sections — assembled dynamically at runtime based on mode. Claude Code's system prompt is 110+ separate instruction strings totaling 16,000-25,000 tokens. The key shift: think of the system prompt as an operating manual for the harness, not a rigid flowchart. The model decides execution order.

### Tip: Treat tool descriptions as a critical engineering surface — vague descriptions drive tool selection errors

- **Source:** [Zylos Research — Prompt Engineering for AI Agent Systems](https://zylos.ai/research/2026-03-30-prompt-engineering-ai-agent-systems-instruction-hierarchies)
- **Date added:** 2026-04-28
- **Context:** Any agent with more than a handful of tools
- **Difficulty:** intermediate

Vague tool descriptions are the primary driver of tool selection errors. With 31 tools adding approximately 4,500 tokens per query, underspecified descriptions waste both tokens and accuracy. Each tool needs explicit guidance: how to use it, when to prefer one over another, what side effects to expect. This applies regardless of whether you're using JSON schemas, MCP, or function calling — the description is the model's only signal about when a tool is appropriate. This is the same principle Cohere and Anthropic emphasize: tool schema design IS prompt engineering.

### Tip: Use instruction hierarchy for defense — system > user > tool output ordering is now trained into models

- **Source:** [Zylos Research — Prompt Engineering for AI Agent Systems](https://zylos.ai/research/2026-03-30-prompt-engineering-ai-agent-systems-instruction-hierarchies)
- **Date added:** 2026-04-28
- **Context:** Agents exposed to untrusted user input or tool output
- **Difficulty:** advanced

Modern models are trained with instruction hierarchy: system prompt instructions override user messages, which override tool outputs. This achieves +63% defense against prompt extraction attacks. Practical implication: put security-critical rules in the system prompt, not in user-facing messages. Caveat: RL-based attacks still achieve 98% bypass rates against current defenses — instruction hierarchy is a layer, not a solution.

### Tip: Even 90%+ single-turn accuracy degrades to 10-15% across full multi-step conversations — plan for coherence loss

- **Source:** [Zylos Research — Prompt Engineering for AI Agent Systems](https://zylos.ai/research/2026-03-30-prompt-engineering-ai-agent-systems-instruction-hierarchies)
- **Date added:** 2026-04-28
- **Context:** Multi-turn agent workflows with bounded iterations
- **Difficulty:** intermediate

Across all production agents, the dominant pattern is plan-execute-observe-repeat. But even when single-turn accuracy exceeds 90%, full multi-step conversation success collapses to 10-15%. Coherence — not single-step capability — is the central unsolved challenge. Practical takeaway: don't benchmark your agent on single turns and assume it scales. Test end-to-end workflows. Add periodic state resets, intermediate verification, or human checkpoints for longer chains.

- [Orchestration](../orchestration.md) — Prompts for multi-agent coordination
- [Reliability](../reliability.md) — Prompt-level guardrails