# Raw Source: OpenAI Agents SDK
# Fetched: 2026-04-28
# Source: https://platform.openai.com/docs/guides/agents

Key concepts extracted:

## Three surfaces
1. Client libraries — direct API clients
2. Agents SDK — server owns orchestration, tools, approvals, state
3. Agent Builder — hosted workflow editor + ChatKit

## SDK architecture
- Agent definitions (typed specialists)
- Models and providers
- Running agents (agent loop, streaming, continuation)
- Sandbox agents (container-based: files, commands, packages, ports, snapshots)
- Orchestration and handoffs (specialist ownership)
- Guardrails and human review (block/pause before risky work)
- Results and state (final output, resumable state, next-turn surfaces)
- Tools (hosted tools, function tools, MCP)
- Integrations and observability (traces for debugging → evaluation loops)
- Voice agents (SDK-only, not Agent Builder)

## Recommendation
SDK track for typed application code, direct MCP control, custom storage, existing product integration