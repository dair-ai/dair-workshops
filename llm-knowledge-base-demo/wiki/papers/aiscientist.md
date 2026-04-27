# AiScientist

AiScientist is useful for this workshop because it turns long-horizon research agents into a workspace design problem.

## Why It Matters

The paper argues that research agents need durable state. Rather than relying only on a long chat transcript, the system stores plans, analyses, logs, and evidence in files. The raw summary reports strong benchmark gains and notes that removing File-as-Bus sharply reduces performance.

## Key Ideas

- File-mediated coordination
- Thin top-level control
- Rich workspace state
- Specialist agents that can recover context from artifacts
- Workspace artifacts as persistent project memory

## Connection To This Demo

This workshop uses the same practical idea. The agent reads `raw/`, writes `wiki/`, files generated answers into `derived/`, and keeps compiler instructions in `prompts/`.

## Related Pages

- [[../concepts/file-as-bus|File-as-Bus]]
- [[../concepts/agent-memory|Agent Memory]]
- [[../maps/research-map|Research Map]]
