# Live Event Outline: Building LLM Knowledge Bases

## Session Goal

Show participants how to build a simple LLM knowledge base from raw AI Papers of the Week summary tables using an agent as the compiler.

## Flow

1. Explain the architecture.
2. Open the `raw/` folder.
3. Show the three weekly source batches.
4. Compile `wiki/index.md`.
5. Create paper pages across the batches.
6. Create concept pages that connect papers.
7. Ask a useful research question.
8. File the answer back into the wiki.
9. Run a lint pass and choose the next page.

## Demo Question

What should builders read first if they want to understand agent memory and long-running research agents?

## Expected Output

The answer should point to AiScientist, Memento, Stateless Decision Memory, AlphaEval, Universal Verifier, File-as-Bus, and Context Compression. It should be saved under `wiki/questions/`.

## Teaching Point

The knowledge base is not a static document collection. It is a loop. Raw notes become wiki pages. Queries become derived outputs. Useful outputs get filed back into the wiki.
