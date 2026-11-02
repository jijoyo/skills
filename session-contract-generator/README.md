# Session Contract Generator

Buy on Agensi: https://agensi.io/skills/session-contract-generator · Free

When you start working on something new, the instinct is to dive in blind. That's how agents (and humans) lose the thread: they forget what the thing is called, where unfinished work lives, what the checkpoints are, and what "done" looks like.

## What it does

- **Bautizo** (name) — what this thing is called, in one line.
- **Presa** (parking lot) — where unfinished work parks so it doesn't get lost.
- **Gates** (checkpoints) — conditions that must be true before you move to the next phase.
- **Huella** (signature) — how "done" looks. The evidence that proves the work is finished, not just claimed.

The generator reads a plan-MD and produces a one-page `CONTRATO.md` with those four fields. Fully offline: reads a local plan-MD, writes a local CONTRATO.md, no network.

## Measured

Built from the actual session-contract workflow used in production (youtube-knowledge-factory). The generator auto-extracts bautizo from the plan title, gates from explicit `gate:` lines or done checkboxes, and huella from acceptance criteria. Tested against a real plan-MD with 2,755 elements.

## Honest limits

Auto-extraction is best-effort. If your plan-MD doesn't follow a recognizable structure, some fields will be defaults you'll want to edit. It's a starting point, not magic. The four fields are a convention, not a law — adapt them to your workflow.
