# DeepSeek V4

DeepSeek V4 is useful for this wiki because it treats million-token context as a default model capability, not an add-on.

## Why It Matters

Long-context agents are expensive to run if every token receives full attention. DeepSeek V4 combines compressed sparse attention, heavily compressed attention, training stability changes, and domain-specialist post-training to make very long context more practical for open model users.

## Key Ideas

- Million-token context as a native target
- Compressed Sparse Attention and Heavily Compressed Attention
- Anticipatory Routing and SwiGLU Clamping for stability
- Domain-specialist post-training with GRPO

## Connection To This Demo

The demo wiki externalizes memory into files, while DeepSeek V4 improves the model substrate that reads those files. Together they show two complementary paths. Store durable knowledge outside the model, then use stronger long-context models to compile and query it.

## Related Pages

- [[../concepts/context-compression|Context Compression]]
- [[../concepts/agent-memory|Agent Memory]]
- [[../maps/research-map|Research Map]]
