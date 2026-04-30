# Raw Source: Cohere Tool Use
# Fetched: 2026-04-28
# Source: https://docs.cohere.com/v2/docs/tool-use

Key concepts:
- tool_plan: model's reflection on next steps before calling tools
- Multi-step tool use: steps 2-3 run multiple times in loop (agents pattern)
- Parallel tool calling: same tool multiple times or different tools
- Fine-grained citations built into Command models
- State management: user → assistant(tool_plan+tool_calls) → tool(results) → assistant(response)
- Schema as prompt engineering: iterate name, description, properties for best results
- Direct answering: model can decide not to use tools