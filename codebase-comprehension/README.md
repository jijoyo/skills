# Codebase Comprehension

Buy on Agensi: https://agensi.io/skills/codebase-comprehension · $9.99

You open a new codebase and have no idea how it works. You read the README (outdated), grep for keywords (misses the architecture), and ask an LLM "explain this" (gets a surface-level answer). This skill gives you a structured, token-budgeted comprehension process.

## What it does

- **L1 — Global Scan** — tech stack, entry points, directory structure. Token budget: ~5K.
- **L2 — Module Partition** — dependencies, modules, imports. Token budget: ~10K.
- **L3 — Data Flow** — how data moves through the system, hooks, state. Token budget: ~15K.
- **L4 — Deep Dive** — core logic, risks, invariants. Token budget: ~20K.

Each layer has a written exit criterion. You don't move to L3 until L2 is done. The result is an architecture report, not a vague summary.

## Measured

Built from the actual methodology used to study OpenCode Desktop (v1.17.15): 4 layers, each with a token budget and a written exit criterion. The scanner L1 was tested against a real codebase (6,500+ files) and produced a correct architecture map in under 30K tokens.

## Honest limits

The token budgets are guidelines, not hard limits. Complex codebases may need more; simple ones may need less. The exit criteria are the real gate — if you can't write the exit criterion, you're not done with that layer.
