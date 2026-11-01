# Ask Your Corpus

Buy on Agensi: https://agensi.io/skills/ask-your-corpus · $4.99

Give your agent search over any folder of `.md`/`.txt` files — private
knowledge it can pick through without a vector database, an index service, or
paying to re-upload your notes somewhere.

## What it does

Two zero-dependency Python scripts:

- `corpus_search.py` — case-insensitive keyword search across a folder tree;
  returns matching files, match counts, and line snippets.
- `build_context.py` — runs the search and stitches the best-matching
  excerpts into a compact context block your agent can actually use.

## Why it works

Long-context models changed the economics of search: you often don't need
embeddings, you need the right 3,000 characters out of your own files. This
skill is the missing folder-level utility — retrieval-quality targeting with
zero infrastructure.

## Honest limits

Keyword search, not semantic: it finds what you spell. The stitched context
is for your agent/model to reason over — searching happens here, answering
lives with your model.
