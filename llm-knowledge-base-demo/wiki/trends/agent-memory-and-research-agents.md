# Trend: Agent Memory and Research Agents

The strongest theme across the three raw weekly summaries is the move from bigger context windows to better memory systems, stronger state management, and outcome-based evaluation.

Several papers point in the same direction. AiScientist stores project state in files. Memento and LightThinker++ compress reasoning traces. Memory Intelligence Agent separates memory management from planning and execution. Memory Transfer Learning shows that abstract procedural memories transfer better than raw traces. Stateless Decision Memory turns agent state into append-only decision logs.

## Why It Matters

Long-running agents fail when they lose the thread of the work, repeat old attempts, or cannot prove why an action succeeded. A durable knowledge base gives them a place to store plans, results, failures, decisions, and reusable insights. This makes the agent less dependent on a single long chat.

The same pattern shows up in self-improving agents. Autogenesis commits validated improvements with lineage and rollback. Automated Weak-to-Strong Researcher coordinates parallel agents through shared findings. Self-Evolving Logic Synthesis edits a real codebase and tests improvements against benchmark circuits.

## Builder Takeaway

For practical projects, a markdown wiki is enough to demonstrate the pattern. Start with raw source notes, compile an index, create concept pages, file every useful answer back into the wiki, and keep the update loop auditable.

## Related Pages

- [[../papers/aiscientist|AiScientist]]
- [[../papers/autogenesis|Autogenesis]]
- [[../papers/memento|Memento]]
- [[../papers/memory-intelligence-agent|Memory Intelligence Agent]]
- [[../papers/stateless-decision-memory|Stateless Decision Memory]]
- [[../concepts/file-as-bus|File-as-Bus]]
- [[../concepts/context-compression|Context Compression]]
