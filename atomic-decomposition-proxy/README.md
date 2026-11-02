# Atomic Decomposition Proxy

Buy on Agensi: https://agensi.io/skills/atomic-decomposition-proxy · $14.99

When a task is too big for one prompt, the instinct is to paste it all in and hope. This fails: the model loses the thread, forgets constraints, or times out.

## What it does

- **Decompose** — takes a compound task and breaks it into atomic leaves (each small enough for one prompt).
- **Execute** — runs each leaf independently against a light model, collecting results.
- **Synthesize** — merges the leaf results into a coherent final answer.

The proxy is OpenAI-compatible: point it at any endpoint (local router, cloud API) and it handles the 3-phase pipeline transparently.

## Measured

Built from real production use: a 64MB JSON of 2,755 communities processed in 3 phases instead of one giant prompt. Zero context overflow, verifiable per-leaf results.

## Honest limits

The decomposition quality depends on the orchestrator model. A weak orchestrator produces bad leaves; a strong one (your top model) produces good ones. The proxy doesn't fix bad decomposition — it just makes it safe.
