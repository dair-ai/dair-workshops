# Prompt: Compile A Paper Page

You are the LLM compiler for this markdown knowledge base.

Create or update one page under `wiki/papers/` for a paper found in `raw/`.

Use this structure:

```markdown
# Paper Title

One paragraph explaining why this paper matters.

## Key Ideas

- Idea one
- Idea two
- Idea three

## Builder Takeaway

Explain how a practitioner can use the idea.

## Connection To This Wiki

Explain which concept pages this paper should link to.

## Related Pages

- [[../concepts/example|Example Concept]]
```

Rules:

- Keep the page readable.
- Link to related concept pages.
- Do not invent paper claims that are not present in `raw/`.
- If metadata is missing, add a "Missing Metadata" section.
