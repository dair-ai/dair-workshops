# Live Event Outline: Building LLM Knowledge Bases

## Session Goal

Show participants how to build a simple LLM knowledge base from raw markdown notes using an agent as the compiler.

## Flow

1. Explain the architecture.
2. Open the `raw/` folder.
3. Compile the first `wiki/index.md`.
4. Create one paper page.
5. Create one concept page.
6. Ask a useful research question.
7. File the answer back into the wiki.
8. Run a lint pass and choose the next page.

## Demo Question

What should builders read first if they want to understand agent memory and long-running research agents?

## Expected Output

The answer should point to AiScientist, Memento, AlphaEval, File-as-Bus, and Context Compression. It should be saved under `wiki/questions/`.

## Teaching Point

The knowledge base is not a static document collection. It is a loop. Raw notes become wiki pages. Queries become derived outputs. Useful outputs get filed back into the wiki.
