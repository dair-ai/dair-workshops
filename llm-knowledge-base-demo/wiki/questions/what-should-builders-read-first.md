# What Should Builders Read First?

For builders interested in LLM knowledge bases, start with the papers and concepts that explain durable state, memory, context compression, and evaluation.

## Recommended Path

1. [[../papers/aiscientist|AiScientist]]
2. [[../concepts/file-as-bus|File-as-Bus]]
3. [[../papers/memento|Memento]]
4. [[../concepts/context-compression|Context Compression]]
5. [[../papers/stateless-decision-memory|Stateless Decision Memory]]
6. [[../papers/alphaeval|AlphaEval]]
7. [[../papers/universal-verifier|Universal Verifier]]

## Why This Path Works

The sequence moves from architecture to durable memory to evaluation. That is the same progression a builder needs when creating a practical knowledge base. First decide where state lives, then decide how it gets compressed, then decide how useful outputs are verified.

## Optional Extension

After the core path, read [[../papers/autogenesis|Autogenesis]] and [[../papers/skill-rag|Skill-RAG]]. Autogenesis shows how an agent can safely update its own operating framework, while Skill-RAG shows how retrieval can become a selective skill instead of a fixed pipeline step.

## Follow-Up Question

What would a weekly maintenance loop look like if this wiki ingested one new AI Papers of the Week issue every Monday?
