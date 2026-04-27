# Research Map

The three raw weekly summaries cluster around one practical question. How should builders make agents reliable when the work is long, tool-heavy, memory-dependent, and hard to evaluate?

## Main Clusters

### Long-Context Infrastructure

DeepSeek V4, Nemotron 3 Super, Attention to Mamba, Neural Computers, and LightThinker++ all address the substrate problem. Agents need cheaper long context, better sequence mixing, compact runtime state, and memory primitives that do not collapse under long reasoning traces.

Related pages:

- [[../papers/deepseek-v4|DeepSeek V4]]
- [[../papers/neural-computers|Neural Computers]]
- [[../concepts/context-compression|Context Compression]]

### Durable Agent Memory

AiScientist, Memento, Memory Intelligence Agent, Memory Transfer Learning, and Stateless Decision Memory point to the same shift. Good memory is not a larger transcript. It is a curated layer of artifacts, summaries, procedures, event logs, and reusable abstractions.

Related pages:

- [[../papers/aiscientist|AiScientist]]
- [[../papers/memento|Memento]]
- [[../papers/memory-intelligence-agent|Memory Intelligence Agent]]
- [[../papers/stateless-decision-memory|Stateless Decision Memory]]
- [[../concepts/context-compression|Context Compression]]
- [[../concepts/agent-memory|Agent Memory]]
- [[../concepts/file-as-bus|File-as-Bus]]

### Self-Improving Agents

Autogenesis, Automated Weak-to-Strong Researcher, Self-Generated World Knowledge, and Self-Evolving Logic Synthesis all treat agent improvement as a loop. The agent proposes changes, tests them against an outcome, and folds useful results back into its operating environment.

Related pages:

- [[../papers/autogenesis|Autogenesis]]
- [[../papers/automated-weak-to-strong-researcher|Automated Weak-to-Strong Researcher]]
- [[../concepts/file-as-bus|File-as-Bus]]

### Evaluation in Real Workflows

AlphaEval, Universal Verifier, LLM-as-a-Verifier, Auto-Diagnose, Muses-Bench, and Automated Weak-to-Strong Researcher highlight the importance of outcome-graded tasks. Agents need evaluations that preserve real constraints, messy inputs, authority conflicts, trajectory evidence, and measurable task progress.

Related pages:

- [[../papers/alphaeval|AlphaEval]]
- [[../papers/universal-verifier|Universal Verifier]]
- [[../papers/automated-weak-to-strong-researcher|Automated Weak-to-Strong Researcher]]
- [[../concepts/production-agent-evaluation|Production Agent Evaluation]]

### Skill and Multi-Agent Limits

Agent Skills in the Wild, Scaling Coding Agents via Atomic Skills, WebXSkill, Single-Agent LLMs vs. Multi-Agent Systems, and Diversity Collapse in Multi-Agent LLMs add a useful warning. More agents, more skills, and more tools do not automatically produce better systems. Retrieval, isolation, compute budgets, and evaluation design decide whether the architecture helps.

## Suggested Next Pages

- Skill Learning for Web Agents
- Multi-Agent Systems Under Fixed Compute
- Diversity Collapse and Isolated Reasoning
- Self-Generated World Knowledge
- Memory Transfer Learning
