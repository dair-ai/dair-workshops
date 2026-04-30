# Evaluation

Tips for evaluating AI agents: benchmarks, testing strategies, LLM-as-judge, and measuring real-world performance.

**Last updated:** 2026-04-28

---

## Tips

### Tip: There is no universal optimal agent architecture — test YOUR configuration

- **Source:** [AgentArch: A Comprehensive Benchmark to Evaluate Agent Architectures](https://arxiv.org/abs/2509.10769) — arxiv / Anthropic
- **Date added:** 2026-04-28
- **Context:** Before committing to any agent architecture (single vs multi, ReAct vs function calling, memory style, thinking tools)
- **Difficulty:** intermediate

AgentArch tested 18 distinct agentic configurations across state-of-the-art LLMs and found strong model-specific architectural preferences. Each model performed best with a different combination of orchestration strategy, agent style, memory architecture, and thinking tool integration. The best models reached only 35.3% success on complex enterprise tasks and 70.8% on simpler ones. The practical implication: don't assume a single "best" architecture. Run your own evals with your specific model and task combination. What works for Claude Opus may not work for GPT-5 or Gemini.

### Tip: Evaluate agents as systems, not models — use realistic workloads

- **Source:** [AI Agent Systems: Architectures, Applications, and Evaluation](https://arxiv.org/abs/2601.01743) — arxiv
- **Date added:** 2026-04-28
- **Context:** When benchmarking or comparing agent implementations
- **Difficulty:** intermediate

The survey emphasizes: evaluate the agent as a system, not just the model. Benchmarks that stress realistic tool use and long-horizon execution (WebArena, SWE-bench, ToolBench, AgentBench) reveal failures that do not appear in static QA. Report not only success rate but also cost/latency, trace completeness, robustness under variability, and safety violations — because these determine whether an agent is deployable under real constraints. Single-metric evaluations hide the dimensions that matter in production.

### Tip: Track evaluation drift across models — prompts that work today may fail tomorrow

- **Source:** [HN — What to Build Instead of AI Agents](https://news.ycombinator.com/item?id=44450160) — HackerNews
- **Date added:** 2026-04-28
- **Context:** Maintaining agent systems that use closed-source models with frequent updates
- **Difficulty:** intermediate

HN commenters repeatedly note: "Look at what happens whenever models are updated. Previous 'good' prompts might not return the expected results." And: "What's good prompting for one model can be bad for another." This is a first-class evaluation concern — your evals need to run not just once but continuously, especially if you depend on API-provided models that change under you. Regression testing for agent behavior should be part of your CI pipeline, not a one-time audit.

### Tip: Multi-agent benefits depend on task structure, not universality — use MASBENCH dimensions

- **Source:** [MAS-Orchestra: Understanding and Improving Multi-Agent Reasoning](https://arxiv.org/abs/2601.14652) — arxiv
- **Date added:** 2026-04-28
- **Context:** Deciding whether to move from single-agent to multi-agent
- **Difficulty:** advanced

MAS-Orchestra's MASBENCH characterizes tasks along five axes: Depth, Horizon, Breadth, Parallel, and Robustness. Their key finding: multi-agent gains depend critically on task structure, verification protocols, and both orchestrator and sub-agent capabilities — rather than holding universally. Before adopting a multi-agent design, evaluate whether your specific task structure actually benefits. Tasks with high parallelism and clear verification criteria benefit most; tasks with simple sequential dependencies often don't.

---

### Tip: Evaluate the full agent trajectory, not just the final output — output-only evals miss 44% of safety violations

- **Source:** [Claw-Eval: Toward Trustworthy Evaluation of Autonomous Agents](https://www.arxiv.org/abs/2604.06132) (2604.06132) — arxiv
- **Date added:** 2026-04-28
- **Context:** Any production agent evaluation pipeline
- **Difficulty:** intermediate

Claw-Eval tested 14 frontier models and found that trajectory-opaque evaluation — checking only final outputs — is systematically unreliable. It misses 44% of safety violations and 13% of robustness failures that trajectory-aware grading catches. The fix: record execution traces, audit logs, and environment snapshots per action, then evaluate against fine-grained rubric items across the full trajectory. If your eval only looks at the final answer, you're blind to nearly half of what goes wrong.

### Tip: Repeat your agent evals — an agent that succeeds once may fail on the exact same task

- **Source:** [On the Reliability of Computer Use Agents](https://arxiv.org/abs/2604.17849) (2604.17849) — arxiv
- **Date added:** 2026-04-28
- **Context:** Any time you report agent evaluation results
- **Difficulty:** intermediate

Research on computer-use agents showed that even when the task and model are unchanged, an agent that succeeds once may fail on a repeated execution. Reliability depends on task specification ambiguity and agent behavior variability across runs. Report Pass^k (consistency across k trials) alongside Pass@k (best-of-k). A model with high Pass@3 but low Pass^3 is lucky, not reliable.

### Tip: Use behavioral rubrics and chain-of-thought for LLM-as-judge — raw scoring is biased

- **Source:** [JudgeGPT](https://www.reddit.com/r/MachineLearning/comments/1rsxcl3) — Reddit + [Universal Verifier](https://arxiv.org/abs/2604.06240) (2604.06240) — arxiv
- **Date added:** 2026-04-28
- **Context:** Using LLMs to evaluate agent outputs
- **Difficulty:** intermediate

LLM judges have well-documented biases: self-family bias (~5-7% score inflation when judge shares model family with evaluee), position bias, verbosity bias, and leniency clustering in smaller models. Countermeasures: (1) use behavioral rubrics with explicit descriptors at each score level, not just "1=bad, 5=good"; (2) have the judge produce chain-of-thought reasoning before scoring; (3) flag when judge and evaluated model share a family. The Universal Verifier paper also recommends separating process and outcome rewards — they give complementary signals.

### Tip: Snapshot-based branching beats linear rollouts for finding agent failures

- **Source:** [DIVERT: Diversity-Induced Evaluation via Branching of Trajectories](https://arxiv.org/abs/2604.21480v1) (2604.21480) — arxiv
- **Date added:** 2026-04-28
- **Context:** Evaluating conversational or multi-turn agents at scale
- **Difficulty:** advanced

Standard evaluation runs full conversations from the beginning repeatedly, re-processing identical prefixes and rarely exploring deep failure modes. DIVERT snapshots the agent state at critical junctions, then branches with diverse user responses from those points. This reuses shared prefixes (saving tokens) and steers evaluation toward unexplored interaction paths. The result: more failures found per evaluation dollar.

- [Reliability](../reliability.md) — Evaluation and reliability go hand in hand
- [Deployment](../deployment.md) — Production evaluation and monitoring