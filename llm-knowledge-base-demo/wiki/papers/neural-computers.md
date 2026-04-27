# Neural Computers

Neural Computers is useful for this wiki because it pushes the boundary between model, memory, computation, and interface.

## Why It Matters

The paper proposes learned runtimes where computation, memory, and I/O collapse into a single neural state. The raw summary describes video-model prototypes that render command-line and graphical interfaces from instructions, pixels, and user actions.

## Key Ideas

- Computation, memory, and I/O inside one learned runtime state
- CLI and GUI prototypes trained from interface traces
- Early runtime primitives for short-horizon control
- A long-term goal of fully neural computers

## Connection To This Demo

This workshop uses a much simpler architecture. Files remain the durable state layer, and the LLM compiles between `raw/` and `wiki/`. Neural Computers points to a more radical future where more of that runtime may live inside the model itself.

## Related Pages

- [[../concepts/agent-memory|Agent Memory]]
- [[../concepts/context-compression|Context Compression]]
- [[../maps/research-map|Research Map]]
