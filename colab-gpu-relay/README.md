# Colab GPU Relay

Buy on Agensi: https://agensi.io/skills/colab-gpu-relay · $4.99

Turn a free Google Colab T4 into a remote worker for heavy jobs your local
machine shouldn't babysit: bulk data crunching, ML runs, files bigger than a
laptop cares about — then relay the results home.

## What it does

- Checked helper (`colab_kit.py`) prepares a Colab session and keeps it
  responsive — no babysitting, no code-change noise in the notebook.
- A relay pattern ships declared payloads to the GPU runtime and brings
  outputs back, so the heavy work never lives on your day machine.
- Batch-friendly: queues jobs instead of one manual session per task.

## What you get

The helper script, the relay recipe with worked examples, and the operational
notes that make a free runtime behave like a queue (limits disclosed, no
pretended SaaS).

## Honest limits

Colab is free, not dedicated: sessions can be reclaimed and quotas vary —
the recipes are written so that losing a session costs minutes, not work.
