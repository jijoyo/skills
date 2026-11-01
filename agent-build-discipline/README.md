# Agent Build Discipline

Buy on Agensi: https://agensi.io/skills/agent-build-discipline · $19.99

One unified operating system for agents that build software. AI agents don't
fail because they lack skill — they fail because they lack discipline: they
arrive remembering nothing, skip stages, declare "done" without evidence, and
drop a 4,000-line pull request on a reviewer at midnight.

## The loop

```
ARRIVE (with memory) → PLAN (gates) → BUILD (TDD) → PROVE (result contract)
→ REVIEW (risk gate) → LEAVE (with a trace)
```

- **Session anchor** — every session reads its own past (plan checklist,
  last trace, open risks) and writes one trace before leaving. No zero-sum
  sessions, no re-exploring the repo from scratch.
- **Phase gates** — each stage refuses to start until the previous one's
  output is verifiably complete. Gate output is binary: pass, or the exact
  list of what is missing.
- **Result contracts** — a structured JSON envelope per phase, with a
  stdlib verifier that confirms every cited evidence path exists. An empty
  "pass" is mechanically impossible: contracts that lie exit 1.
- **TDD gate** — red before green, stated as a gate rather than taste.
- **PR risk gate** — one number decides review readiness: changed-line cap
  plus declared high-risk areas (auth, migrations, entry points). Counting,
  not judgment — monster PRs get split before they get reviewed.

## What you get

The discipline (SKILL.md), a ten-minute setup guide, a result-contract
template plus phase-gates declaration, and a contract verifier
(`check_contract.py`, Python 3.8+ stdlib). Proof at every step: verified →
exit 0; lies → exit 1 with the exact list.

## Honest limits

This is discipline, not magic: it cannot stop an agent from writing bad code,
it makes bad process impossible to hide in seconds.

Proven shipping a real healthcare app through months of agent-driven
development.
