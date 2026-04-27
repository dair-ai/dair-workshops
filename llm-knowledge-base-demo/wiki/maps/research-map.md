# Research Map

The current raw notes cluster around one practical question. How should agents preserve and reuse knowledge across long-running work?

## Main Clusters

### Durable Workspace State

AiScientist and the workshop structure both use the filesystem as the shared state layer. The important move is to store plans, evidence, logs, and outputs as durable artifacts instead of keeping everything in chat history.

Related pages:

- [[../papers/aiscientist|AiScientist]]
- [[../concepts/file-as-bus|File-as-Bus]]

### Memory and Compression

Memento, Memory Intelligence Agent, and Memory Transfer Learning all point to a shift from storing everything to storing useful abstractions. Good memory is not a larger transcript. It is a compressed, reusable representation of what matters.

Related pages:

- [[../papers/memento|Memento]]
- [[../papers/memory-intelligence-agent|Memory Intelligence Agent]]
- [[../concepts/context-compression|Context Compression]]
- [[../concepts/agent-memory|Agent Memory]]

### Evaluation in Real Workflows

AlphaEval and Automated Weak-to-Strong Researcher highlight the importance of outcome-graded tasks. Agents need evaluations that preserve real constraints, messy inputs, and measurable task progress.

Related pages:

- [[../papers/alphaeval|AlphaEval]]
- [[../papers/automated-weak-to-strong-researcher|Automated Weak-to-Strong Researcher]]
- [[../concepts/production-agent-evaluation|Production Agent Evaluation]]

## Suggested Next Pages

- Skill Learning for Web Agents
- Recursive Reading for Large Source Collections
- When Multi-Agent Systems Help
- The Difference Between Memory, Context, and Knowledge
