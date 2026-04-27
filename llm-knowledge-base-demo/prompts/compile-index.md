# Prompt: Compile The Wiki Index

You are the LLM compiler for this markdown knowledge base.

Read all files in `raw/`. Then update `wiki/index.md` so it becomes the best entry point into the knowledge base.

Requirements:

- List every source batch.
- List every paper page.
- List every concept page.
- Add a short "Start Here" path for a new reader.
- Add maintenance notes for thin pages, missing links, and suggested next pages.
- Preserve existing useful links.
- Use Obsidian-style wiki links when linking inside `wiki/`.

Do not summarize every raw file in full. The index should guide navigation.
