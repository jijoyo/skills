# MCP Token Diet

Buy on Agensi: https://agensi.io/skills/mcp-token-diet · $9.99

Your agent pays a hidden tax: every connected Model Context Protocol server
dumps its entire tool library into every request. Twenty minutes of flying
and your prompt is 60% tool definitions you never call.

## What it does

- **Audit** — inventories every connected MCP server and what it actually
  contributes; flags idle platforms and duplicated tools.
- **Lazy-loading pattern** — replaces hundred-tool catalogs with one loader:
  the agent sees the 7-8 core tools it always needs plus a single
  `load_tool(name)` entry; full instructions load on demand.
- **OpenCode plugin included** — automatic `fetch` interception, so it works
  without yak-shaving your client.

## Measured

49 tools → 9 visible, roughly −80% request overhead in a real client
(OpenCode). Savings scale with how many MCP servers you connect — the more
plugged-in you are, the more you save.

## Honest limits

Lazy-loading redirects tool discovery through one extra call — the audit
tells you which servers are worth it vs which deserve losing entirely.
