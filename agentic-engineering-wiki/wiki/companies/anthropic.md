# Anthropic

- **Last updated:** 2026-04-28
- **Key resources:**
  - Docs: https://docs.anthropic.com/en/docs/build-with-claude
  - Engineering blog: https://www.anthropic.com/engineering
  - Research blog: https://www.anthropic.com/research

## Recent Publications

| Date | Title | Type | Key Takeaway |
|------|-------|------|--------------|
| 2026-04 | [How Tool Use Works](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/how-tool-use-works) | docs | Three-tier tool model: client tools, Anthropic-schema tools (trained-in), server tools. Agentic loop with `pause_turn` handling. |
| 2026-04 | [Tool Use Overview](https://docs.anthropic.com/en/docs/build-with-claude/tool-use/overview) | docs | Strict tool use (`strict: true`), server tools, tool pricing model |
| 2026-04 | [Building with Claude (claude-api skill)](https://docs.anthropic.com/en/docs/agents-and-tools) | docs | Agent Skills system with progressive disclosure; Managed Agents (beta) with server-managed stateful agents |

## Agent-Specific Resources

- [Building with Claude: Tool Use](https://docs.anthropic.com/en/docs/build-with-claude/tool-use/overview)
- [Building with Claude: Extended Thinking](https://docs.anthropic.com/en/docs/build-with-claude/extended-thinking)
- [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook)
- [Agent Skills Overview](https://docs.anthropic.com/en/docs/agents-and-tools/agent-skills/overview)
- [Managed Agents (beta)](https://docs.anthropic.com/en/docs/agents-and-tools)

## Recurring Themes

- **Tool use as a typed contract** — Anthropic frames tools as a structured interface between application and model, not as free-form prompting
- **Progressive disclosure** for context efficiency — skills load only relevant documentation
- **Trained-in schemas** — Pre-built tool schemas (bash, text_editor) that the model handles more reliably than custom equivalents