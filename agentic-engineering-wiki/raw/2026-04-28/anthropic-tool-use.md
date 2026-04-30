# Raw Source: Anthropic Tool Use Docs
# Fetched: 2026-04-28
# Source: https://docs.anthropic.com/en/docs/build-with-claude/tool-use/overview
# Source: https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/how-tool-use-works

Key concepts extracted:

## Tool Use Types
1. User-defined client tools: schema + execution in your app, agentic loop
2. Anthropic-schema client tools: bash, text_editor, computer, memory — trained-in schemas
3. Server-executed tools: web_search, web_fetch, code_execution, tool_search — Anthropic infrastructure

## Agentic Loop
while stop_reason == "tool_use":
  execute tools
  send tool_result back
  continue

Handle pause_turn for server tools — work isn't finished

## Strict Tool Use
strict: true ensures schema conformance

## When to use tools
- Actions with side effects
- Fresh/external data
- Structured guaranteed-shape outputs
- Calling existing systems

## Anti-pattern
Regex-parsing model output to extract decisions → should be tool calls