# Skill-RAG

Skill-RAG is useful for this wiki because it reframes retrieval as a decision made by the agent, not a fixed step that always runs.

## Why It Matters

Standard RAG retrieves on every query, even when the model already knows the answer. Skill-RAG probes hidden states to detect likely knowledge failure, then routes the query to a retrieval strategy matched to the gap. This makes retrieval more selective and more skill-like.

## Key Ideas

- Hidden-state probing for retrieval triggers
- Different retrieval strategies for different failure modes
- Efficiency gains from skipping unnecessary retrieval
- RAG as composable retrieval skills

## Connection To This Demo

The wiki can use the same principle. A query should not blindly scan every file. It should first decide whether it needs paper pages, concept pages, trend pages, raw summaries, or derived outputs.

## Related Pages

- [[../concepts/context-compression|Context Compression]]
- [[../concepts/agent-memory|Agent Memory]]
- [[../maps/research-map|Research Map]]
