# OpenAI

- **Last updated:** 2026-04-28
- **Key resources:**
  - Platform docs: https://platform.openai.com/docs
  - Engineering blog: https://openai.com/blog
  - Cookbook: https://cookbook.openai.com

## Recent Publications

| Date | Title | Type | Key Takeaway |
|------|-------|------|--------------|
| 2026-04 | [Agents SDK Guide](https://platform.openai.com/docs/guides/agents) | docs | Three surfaces: SDK (code-first), Agent Builder (hosted visual editor), client libraries. Sandbox agents with container execution. |
| 2026-04 | [Orchestration and Handoffs](https://platform.openai.com/docs/guides/agents/orchestration) | docs | Specialist agents with explicit ownership and handoff patterns |
| 2026-04 | [Guardrails and Human Review](https://platform.openai.com/docs/guides/agents/guardrails-approvals) | docs | Built-in guardrail and approval patterns for risky operations |
| 2026-04 | [Sandbox Agents](https://platform.openai.com/docs/guides/agents/sandboxes) | docs | Container-based execution with files, commands, packages, snapshots, mounts |

## Agent-Specific Resources

- [OpenAI Agents SDK](https://platform.openai.com/docs/guides/agents-sdk)
- [Function Calling Guide](https://platform.openai.com/docs/guides/function-calling)
- [Agent Builder (hosted workflow editor)](https://platform.openai.com/docs/guides/agent-builder)
- [Voice Agents Guide](https://platform.openai.com/docs/guides/voice-agents)
- [Agent Evaluations](https://platform.openai.com/docs/guides/agent-evals)

## Recurring Themes

- **Specialist decomposition** — Break agents into focused specialists with clear ownership boundaries
- **Safety by design** — Guardrails and human review built into the SDK, not added later
- **Surface flexibility** — Same models, different deployment patterns: code-first vs visual builder vs simple API