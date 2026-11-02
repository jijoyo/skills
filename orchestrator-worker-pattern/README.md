# Orchestrator-Worker Pattern

Buy on Agensi: https://agensi.io/skills/orchestrator-worker-pattern · Free

When a file is too big for the LLM's context — a 64MB JSON, a million-line log, a CSV with thousands of rows — the instinct is to paste it in and ask the model to "process this." That fails: the context saturates, instructions get lost, the model times out, or it silently forgets the middle.

## What it does

- **Orchestrator** (your most capable model) — thinks about the goal, designs the processing logic, writes a small specialized script, runs it, and inspects the final result. It never touches the raw data directly.
- **Worker** (a script + a light model) — does the heavy lifting: iterating over millions of lines, doing math, transforming rows. When a step needs intelligence, the script calls a light, cheap model on each element individually.

Includes a ready-to-adapt generic worker template that auto-detects JSON/CSV/plain-text and calls the light model once per element.

## Measured

Built from the actual pattern used to process 64MB JSON of 2,755 communities (youtube-knowledge-factory). The orchestrator read only the first 3 entries to see the shape, wrote the task, ran the worker with `--model qwen36-mx`, and read back the output. Total cost: a few dollars of light-model tokens. Zero context crashes.

## Honest limits

It trades latency for safety: one model call per element is slower than one big call, but it never crashes on context limits. For small files, just read them directly — don't reach for this pattern out of habit. The template is sequential by default (`--parallel 1`), which is correct for local GPU setups. In cloud, raise `--parallel` to exploit API concurrency.
