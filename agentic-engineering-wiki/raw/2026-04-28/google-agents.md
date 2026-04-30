# Raw Source: Google Gemini Agents
# Fetched: 2026-04-28
# Source: https://ai.google.dev/gemini-api/docs/agents
# Source: https://ai.google.dev/gemini-api/docs/prompting-strategies#agentic-workflows

Key concepts extracted:

## Agent definition
Systems leveraging Gemini models + tools + reasoning for complex multi-step tasks

## Components
- Gemini models (core intelligence)
- Tools (built-in: Google Search, Maps, Code Execution; or custom)
- Function calling (connect custom tools/APIs)
- Thinking (enhanced reasoning and planning)
- Long context (state over extended interactions)

## Available agents
- Deep Research Agent: autonomous multi-step research, market analysis, due diligence

## Prompting strategy
System instruction template improved performance ~5% across agentic benchmarks:
- Persist through errors
- Assess risks before acting
- Plan proactively
- Verify tool outputs against original goal

## Agent frameworks
- LangChain/LangGraph: stateful graph-based flows
- LlamaIndex: RAG-enhanced workflows
- CrewAI: collaborative role-playing agents
- Vercel AI SDK: frontend-focused
- Google ADK: interoperable agent orchestration