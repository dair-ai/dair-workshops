# Prompt: Compile A Concept Page

You are the LLM compiler for this markdown knowledge base.

Create or update one page under `wiki/concepts/` by synthesizing patterns across multiple paper pages and raw notes.

Use this structure:

```markdown
# Concept Name

Plain-language explanation of the concept.

## Core Idea

Explain the underlying pattern.

## Why It Helps

Explain why builders should care.

## In The Source Notes

Name the source papers that support the concept.

## In This Demo

Explain how the concept appears in the workshop knowledge base.

## Related Pages

- [[../papers/example|Example Paper]]
```

Rules:

- Prefer plain language over jargon.
- Add backlinks to paper pages.
- Identify missing source evidence when the concept is too thin.
