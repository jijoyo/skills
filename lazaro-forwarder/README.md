# Lázaro Forwarder

Buy on Agensi: https://agensi.io/skills/l-zaro-forwarder · $4.99

When you run multiple LLM sessions (local or cloud), they don't talk to each other by default. Each session is isolated. You need a human to copy-paste between them, or you lose context when one session dies.

## What it does

- **kvproxy** — a transparent forwarder that sits between your agent and the model endpoint. Forwards everything intact (including streaming), measures per-turn KV cache effectiveness (HIT/MISS), and exposes a `/status` endpoint. Works with any OpenAI-compatible endpoint: local router (`:8080`) or cloud API.
- **The Lázaro protocol** — the rules for how agents talk to each other over that forwarder without stepping on each other: announcement, signature, acknowledgment, receiver discipline, hop limits, and honest cost accounting.

## Measured

Built from the actual inter-agent communication system used in production (montar-modelos). The protocol was measured against real incidents: hot session lost (measured), drip-feed prefill (4×27K measured), 3-hop consolidation (tested). The forwarder is transparent by design — it doesn't modify requests or responses.

## Honest limits

The protocol assumes OpenCode (or similar) as the agent runtime. The concepts transfer to any system with sessions, but the commands are OpenCode-specific. kvproxy is in-memory only (last 20 turns), never writes to disk. If something breaks, it's not the forwarder.
