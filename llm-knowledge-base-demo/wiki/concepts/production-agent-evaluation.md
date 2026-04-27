# Production Agent Evaluation

Production agent evaluation asks whether an agent can complete realistic work under messy constraints, not only whether it can solve clean benchmark tasks.

## Core Idea

Real workflows include implicit requirements, partial information, subjective judgment, UI behavior, and changing expectations. Evaluating only isolated model responses misses these constraints.

## In The Source Notes

AlphaEval is the main source for this concept. Automated Weak-to-Strong Researcher adds another angle by showing that measurable research progress depends on careful metric design.

## Practical Use

When building an LLM knowledge base, evaluation should check whether the wiki helps with real research work. Useful tests include finding relevant papers, explaining trends, creating event outlines, and identifying missing source material.

## Related Pages

- [[../papers/alphaeval|AlphaEval]]
- [[../papers/automated-weak-to-strong-researcher|Automated Weak-to-Strong Researcher]]
