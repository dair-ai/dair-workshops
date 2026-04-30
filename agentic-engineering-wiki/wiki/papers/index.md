# Research Papers

Key arxiv papers relevant to AI agent engineering, distilled into practical takeaways.

**Last updated:** 2026-04-28

**Tracked categories:** cs.AI, cs.CL, cs.LG

---

## Papers

### Architectural Design Decisions in AI Agent Harnesses

- **arxiv:** [2604.18071](https://arxiv.org/abs/2604.18071)
- **Date:** 2026-04-20
- **Authors:** Study of 70 publicly available agent-system projects
- **Category:** cs.AI

**What:** Protocol-guided empirical study of 70 agent-system projects, identifying recurring design dimensions and architectural patterns in agent infrastructure.

**Key finding:** Five recurring design dimensions: subagent architecture, context management, tool systems, safety mechanisms, and orchestration. Registry-oriented tool systems remain dominant; MCP and plugin-oriented extensions are emerging. High-assurance audit is rare.

**Practical takeaway:** When designing agent infrastructure, these 5 dimensions are your architecture checklist. Most projects favor file-persistent, hybrid, hierarchical context strategies. If you're building a framework or choosing one, compare against these patterns.

---

### UniToolCall: Unifying Tool-Use for LLM Agents

- **arxiv:** [2604.11557](https://arxiv.org/abs/2604.11557)
- **Date:** 2026-04-13
- **Authors:** —
- **Category:** cs.AI

**What:** Unified framework for tool learning that standardizes toolset construction, dataset generation, and evaluation.

**Key finding:** Fine-tuned Qwen3-8B achieves 93.0% single-turn Strict Precision on distractor-heavy settings, outperforming GPT, Gemini, and Claude. Uses 22k+ tools and 390k+ training instances.

**Practical takeaway:** Smaller fine-tuned models can match or beat frontier models on tool use when trained on well-structured data. The QAOA (Query-Action-Observation-Answer) format is a useful evaluation standard.

**Limitations:** Fine-tuning requires resources. Results may not generalize to entirely unseen tool types.

---

### AgentArch: Benchmark for Agent Architecture Evaluation

- **arxiv:** [2509.10769](https://arxiv.org/abs/2509.10769)
- **Date:** 2025
- **Authors:** Multiple institutions
- **Category:** cs.AI

**What:** Evaluates 18 agentic configurations across LLMs spanning orchestration strategy, agent style (ReAct vs function calling), memory architecture, and thinking tools.

**Key finding:** No universally optimal agent architecture. Model-specific preferences. Best models: 35.3% on complex enterprise tasks, 70.8% on simpler tasks. Even top models lack reliability over multiple trials.

**Practical takeaway:** Don't assume a one-size-fits-all architecture. Run evals with YOUR specific model + task combination before committing.

---

### Team of Thoughts: Heterogeneous Multi-Agent Systems

- **arxiv:** [2602.16485](https://arxiv.org/abs/2602.16485)
- **Date:** 2026-02-18
- **Authors:** —
- **Category:** cs.CL, cs.AI

**What:** Heterogeneous MAS framework treating diverse models as specialized tools with orchestrator-driven paradigm.

**Key finding:** 96.00% on AIME24 and 77.91% on LiveCodeBench, significantly outperforming homogeneous baselines (80.00% and 65.93%).

**Practical takeaway:** Mix models in multi-agent systems — each model has different strengths. Use orchestrator calibration and agent self-assessment to match agents to subtasks.

---

### ASA: Training-Free Fix for Tool-Calling Reliability

- **arxiv:** [2602.04935](https://arxiv.org/abs/2602.04935)
- **Date:** 2026-02-04
- **Authors:** —
- **Category:** cs.SE, cs.AI

**What:** Training-free, inference-time controller that fixes the "Lazy Agent" failure mode where models know they should use tools but don't.

**Key finding:** Improves strict tool-use F1 from 0.18 to 0.50 while reducing false positive rate from 0.15 to 0.05. Uses ~20KB portable assets, no weight updates.

**Practical takeaway:** The "Lazy Agent" pattern is a real, measurable failure mode. When debugging tool-use issues, check whether the model's activations indicate tool intent even when it doesn't call tools.

---

### xMemory: Beyond RAG for Agent Memory

- **arxiv:** [2602.02007](https://arxiv.org/html/2602.02007v3)
- **Date:** 2026
- **Authors:** —
- **Category:** cs.AI

**What:** Hierarchical memory architecture that moves beyond flat RAG similarity retrieval for agent conversations.

**Key finding:** Fixed top-k RAG returns redundant context from correlated spans. Hierarchical retrieval with theme-based organization gives consistent gains in answer quality and token efficiency.

**Practical takeaway:** If your agent has memory, don't use flat vector similarity retrieval. Build hierarchical memory that separates semantic components and retrieves diverse themes, not similar chunks.

---

### Memory for Autonomous LLM Agents (Survey)

- **arxiv:** [2603.07670](https://arxiv.org/html/2603.07670v1)
- **Date:** 2026-03
- **Authors:** —
- **Category:** cs.AI

**What:** Structured account of memory design in LLM agents from 2022-2026. Formalizes memory as write-manage-read loop.

**Key finding:** Three generations: prompt compression → RAG → learned memory policies (AgeMem with RL-optimized memory ops). MemoryArena: models scoring near-perfect on LoCoMo plummet to 40-60% in active decision-relevant memory tests. RAG-based agents beat long-context baselines but retrieval quality is the bottleneck.

**Practical takeaway:** Long context is not memory. Build explicit memory systems with write paths. Test memory in decision-making contexts, not just recall.

---

### MAS-Orchestra + MASBENCH

- **arxiv:** [2601.14652](https://arxiv.org/abs/2601.14652)
- **Date:** 2026-01-21
- **Authors:** —
- **Category:** cs.AI, cs.CL

**What:** Formulates MAS orchestration as function-calling RL. Introduces MASBENCH with 5 task characterization axes.

**Key finding:** Multi-agent benefits depend on: task structure, verification protocols, orchestrator and sub-agent capabilities. Not universal.

**Practical takeaway:** Use the 5 dimensions (Depth, Horizon, Breadth, Parallel, Robustness) to decide whether multi-agent is worth it for your specific task.

---

### VMAO: Verified Multi-Agent Orchestration

- **arxiv:** [2603.11445](https://arxiv.org/pdf/2603.11445)
- **Date:** 2026-03
- **Authors:** —
- **Category:** cs.AI

**What:** Plan-Execute-Verify-Replan framework with independent LLM-based verifier as orchestration-level coordination signal.

**Key finding:** Improves answer completeness from 3.1 to significantly higher on 25 market research queries. Configurable stop conditions balance quality against resource usage.

**Practical takeaway:** Add a verification step AFTER execution, not just during planning. An independent model checking results is more reliable than self-verification.

---

### AOrchestra: Automatic Sub-Agent Creation

- **arxiv:** [2602.03786](https://arxiv.org/abs/2602.03786)
- **Date:** 2026-02-03
- **Authors:** —
- **Category:** cs.AI, cs.CL

**What:** Framework-agnostic agent abstraction as (Instruction, Context, Tools, Model) tuple. Auto-creates sub-agents on demand.

**Key finding:** 16.28% relative improvement against strongest baseline on GAIA, SWE-Bench, Terminal-Bench.

**Practical takeaway:** Consider dynamic sub-agent creation rather than a fixed set of pre-defined agents. The tuple abstraction (Instruction, Context, Tools, Model) is a useful way to think about agent composition.

---

## Related

- [Tips](../tips/) — Papers often produce actionable tips
- [Timeline](../timeline.md) — Chronological context for research developments