# Memento

Memento is a useful example of context compression for reasoning models.

## Why It Matters

The paper teaches models to summarize reasoning blocks into compact mementos and continue from those summaries. The raw summary reports large KV-cache reductions and practical throughput gains. For builders, the broader lesson is that durable compressed state can be more useful than storing every detail.

## Key Ideas

- Reasoning block segmentation
- Compact mementos
- Context reduction
- Continued reasoning from summaries
- Throughput gains from shorter active context

## Connection To This Demo

The wiki is the workshop version of a memento. Raw weekly notes are compressed into paper pages, concept pages, maps, and question answers.

## Related Pages

- [[../concepts/context-compression|Context Compression]]
- [[../concepts/agent-memory|Agent Memory]]
