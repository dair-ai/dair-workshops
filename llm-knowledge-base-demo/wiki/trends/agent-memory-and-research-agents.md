# Trend: Agent Memory and Research Agents

The strongest theme in the current source set is the move from bigger context windows to better externalized memory.

Several papers point in the same direction. AiScientist stores project state in files. Memento compresses reasoning traces into smaller summaries. Memory Intelligence Agent separates memory management from planning and execution. Memory Transfer Learning shows that abstract procedural memories transfer better than raw traces.

## Why It Matters

Long-running agents fail when they lose the thread of the work. A durable knowledge base gives them a place to store plans, results, failures, decisions, and reusable insights. This makes the agent less dependent on a single long chat.

## Builder Takeaway

For practical projects, a markdown wiki is enough to demonstrate the pattern. Start with raw source notes, compile an index, create concept pages, and file every useful answer back into the wiki.

## Related Pages

- [[../papers/aiscientist|AiScientist]]
- [[../papers/memento|Memento]]
- [[../papers/memory-intelligence-agent|Memory Intelligence Agent]]
- [[../concepts/file-as-bus|File-as-Bus]]
- [[../concepts/context-compression|Context Compression]]
