# Stateless Decision Memory

Stateless Decision Memory is useful for this wiki because it applies distributed-systems discipline to agent memory.

## Why It Matters

Stateful agents become hard to scale when many instances run across containers or tenants. Decision Process Memory replaces live per-agent state with immutable event logs. Any instance can reconstruct context by replaying the log, which makes the system easier to audit, isolate, and scale.

## Key Ideas

- Append-only decision logs
- Stateless projection from event history
- Replayable rationale trails
- Per-event provenance and multi-tenant isolation

## Connection To This Demo

The workshop wiki is not an event-sourced system, but it follows the same instinct. Durable files make decisions inspectable and recoverable. A future version could add an append-only `derived/decisions.md` log to record each compiler pass.

## Related Pages

- [[../concepts/agent-memory|Agent Memory]]
- [[../concepts/file-as-bus|File-as-Bus]]
- [[../trends/agent-memory-and-research-agents|Trend: Agent Memory and Research Agents]]
