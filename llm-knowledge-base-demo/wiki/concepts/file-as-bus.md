# File-as-Bus

File-as-bus is a coordination pattern where agents communicate through durable files rather than only through chat messages or in-memory state.

## Core Idea

The workspace becomes the source of truth. Agents write plans, summaries, logs, experiments, and decisions into files. Later agents can inspect the files and recover the project state without needing the full conversation history.

## Why It Helps

- It makes agent work inspectable.
- It reduces dependence on long context windows.
- It allows specialized agents to join later.
- It creates a record that can be linted, summarized, and reused.

## In This Demo

The `raw/` folder is the ingest layer, `wiki/` is the compiled knowledge layer, `derived/` stores generated outputs, and `prompts/` stores repeatable compiler instructions.

## In The Source Notes

AiScientist is the main example because it routes plans, analyses, code, logs, and evidence through versioned workspace artifacts. Automated Weak-to-Strong Researcher uses a shared forum and uploaded codebase snapshots so parallel agents can build on one another's results. Autogenesis makes self-improvements inspectable through lineage and rollback. Stateless Decision Memory uses immutable event logs so agent instances can reconstruct state without owning live memory.

## Related Pages

- [[../papers/aiscientist|AiScientist]]
- [[../papers/automated-weak-to-strong-researcher|Automated Weak-to-Strong Researcher]]
- [[../papers/autogenesis|Autogenesis]]
- [[../papers/stateless-decision-memory|Stateless Decision Memory]]
- [[../maps/research-map|Research Map]]
