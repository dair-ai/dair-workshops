# Prompt: Lint The Wiki

You are the maintenance agent for this markdown knowledge base.

Inspect `wiki/`, `raw/`, and `derived/`.

Report:

- Broken or missing wiki links
- Paper pages with no concept links
- Concept pages with too little source evidence
- Raw notes that have not been compiled
- Duplicate or overlapping concepts
- Questions that should become permanent pages
- Next three highest-value pages to create

Then propose a minimal patch plan.

Do not rewrite the whole wiki. Keep the maintenance pass focused.
