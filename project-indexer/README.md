# Project Indexer

Buy on Agensi: https://agensi.io/skills/project-indexer · $4.99

Generate INDEX.md for any project: one small note per folder, a tree
overview, and a key-files table. Agents (and humans) stop re-exploring a
folder they last saw a week ago — one page answers the routing question in
seconds, ~2K tokens.

## How each folder's note is chosen

First hit wins:

1. **Your overrides** — `path=note` lines in the project's `.index-notes`
2. **The folder speaks** — first meaningful line of its `AGENTS.md`/`README.md`
3. **The count** — "7 files", when nothing else exists

Honest by construction: derived from what exists, overridable in two seconds
(`echo 'src=app entry points' >> .index-notes` and rerun).

## What one INDEX.md contains

- Structure overview (top 2 levels, caches ignored; `tree` optional)
- One collapsible `[!NOTE]` callout per top-level folder — renders in
  Obsidian, GitHub, VS Code
- A key-files table (`AGENTS.md`, `README.md`, `package.json` with purpose)

## What you get

A single bash script (`indexer.sh`, no build step, zero dependencies beyond
GNU coreutils — Linux out of the box, macOS via `brew install coreutils`)
plus the discipline docs and the agent hook (read INDEX.md first).

Pair it with folder search (e.g. Ask Your Corpus): the map says *where*;
the search digs *into*.
