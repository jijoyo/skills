# Project Brain Map

Buy on Agensi: https://agensi.io/skills/project-brain-map · $9.99

Give every project a small, honest architecture graph your agents can trust:
declared nodes (never invented), recalculated line counts, one glanceable
offline HTML page, and a staleness gate that turns "stale docs" from a polite
wish into a red exit code.

## The idea in one line

A graph nobody keeps fresh is a lie. So the map is declared by hand (what you
verified), recomputed on every build (what you can measure), and gated before
commits (what you cannot forget).

## Three commands

- `init` — scaffolds `ops-brain/`: a tiny declaration (`id / file / role`)
  plus an offline viewer.
- `build` — verifies every declared file exists (an invented map fails
  loudly), recomputes line counts, writes `brain-graph.json`, and refreshes
  the viewer. Works from `file://`, no server.
- `check` — the anti-rot gate: compares reality against the stored graph;
  exit 0 = FRESH, exit 1 = STALE with the exact drifts. Drop it into your
  git pre-commit hook or CI step.

Node id prefixes (`svc:`, `doc:`, `plan:`, `data:`, `tool:`, `test:`)
color-code the viewer.

## What you get

A zero-dependency generator (`brain_map.js`, Node stdlib only) and the
discipline docs. No npm install, no network, no database.

Proven in 7 repositories running live graphs with a simple rule: a stale
graph is debt.
