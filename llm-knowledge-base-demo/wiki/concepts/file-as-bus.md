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

## Related Pages

- [[../papers/aiscientist|AiScientist]]
- [[../maps/research-map|Research Map]]
