# LLM Knowledge Base Demo

This folder is a workshop-ready example of a Karpathy-style LLM knowledge base. The goal is to show how an agent can read raw markdown notes and compile them into a structured wiki without a vector database.

## Folder Structure

```text
raw/
  ai-papers-of-the-week/
wiki/
  papers/
  concepts/
  trends/
  maps/
  questions/
derived/
prompts/
```

## How To Run The Demo

1. Open this folder in your editor.
2. Ask an agent to read `raw/ai-papers-of-the-week/`.
3. Use `prompts/compile-index.md` to update `wiki/index.md`.
4. Use `prompts/compile-paper-page.md` to create or improve paper pages.
5. Use `prompts/compile-concept-page.md` to create cross-paper concept pages.
6. Ask a research question and file the answer into `wiki/questions/` or `derived/`.
7. Run `prompts/lint-wiki.md` to identify missing links, weak pages, and useful next questions.

## Demo Narrative

The raw folder is the ingest layer. The wiki folder is the compiled knowledge layer. The derived folder stores useful outputs from queries. The prompts folder makes the workflow repeatable.

The key idea is simple. The knowledge base gets better every time the agent reads, compiles, queries, and files the output back into the wiki.

## Source Inspiration

The sample raw notes are copied from DAIR.AI's AI Papers of the Week weekly summary tables:

https://github.com/dair-ai/AI-Papers-of-the-Week
