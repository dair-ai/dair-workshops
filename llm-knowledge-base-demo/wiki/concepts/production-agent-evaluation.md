# Production Agent Evaluation

Production agent evaluation asks whether an agent can complete realistic work under messy constraints, not only whether it can solve clean benchmark tasks.

## Core Idea

Real workflows include implicit requirements, partial information, subjective judgment, UI behavior, and changing expectations. Evaluating only isolated model responses misses these constraints.

## In The Source Notes

AlphaEval is the main source for this concept because it evaluates agent products on production-like tasks from real companies. Universal Verifier adds trajectory-level evaluation for computer-use agents. LLM-as-a-Verifier shows a lightweight test-time ranking method for choosing among candidate outputs. Auto-Diagnose shows what production evaluation looks like inside an existing developer workflow. Automated Weak-to-Strong Researcher adds another angle by showing that measurable research progress depends on careful metric design.

## Practical Use

When building an LLM knowledge base, evaluation should check whether the wiki helps with real research work. Useful tests include finding relevant papers, explaining trends, creating event outlines, and identifying missing source material.

## Related Pages

- [[../papers/alphaeval|AlphaEval]]
- [[../papers/universal-verifier|Universal Verifier]]
- [[../papers/automated-weak-to-strong-researcher|Automated Weak-to-Strong Researcher]]
