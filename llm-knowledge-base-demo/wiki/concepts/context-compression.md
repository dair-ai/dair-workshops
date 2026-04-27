# Context Compression

Context compression is the practice of reducing large working traces into compact summaries, state representations, or retrieval decisions that preserve the information needed for future reasoning.

## Core Idea

The goal is not to remember every token. The goal is to keep the conclusions, constraints, decisions, and open questions that help future work continue.

## In The Source Notes

Memento is the clearest example. It compresses reasoning blocks into smaller mementos. LightThinker++ adds explicit memory primitives for committing, expanding, and folding reasoning state. DeepSeek V4 compresses attention at the model architecture level so million-token contexts become practical. Skill-RAG compresses the retrieval decision by asking whether retrieval is needed before calling a retriever.

## In This Demo

The wiki is a compression layer. Each paper page compresses a raw paper entry. Each concept page compresses patterns across multiple papers. Each question page compresses an exploration into a reusable answer.

## Related Pages

- [[../papers/memento|Memento]]
- [[../papers/deepseek-v4|DeepSeek V4]]
- [[../papers/skill-rag|Skill-RAG]]
- [[agent-memory|Agent Memory]]
