# Raw Source: Stripe Agent Toolkit
# Fetched: 2026-04-28
# Source: https://docs.stripe.com/agents

Key concepts:
- Multi-framework support: OpenAI Agents SDK, Vercel AI SDK, LangChain, CrewAI
- Python + TypeScript
- Works with any LLM provider supporting function calling
- Strong recommendation: use restricted API keys (rk_*)
- Agent behavior is non-deterministic — use sandbox and evals
- Example: create_stripe_agent_toolkit → Agent(tools=toolkit.get_tools())