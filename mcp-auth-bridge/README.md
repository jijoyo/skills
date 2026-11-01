# MCP Auth Bridge

Buy on Agensi: https://agensi.io/skills/mcp-auth-bridge-connect-oauth-mcp-servers-to-opencode · $7.99

Official MCP servers that demand OAuth2 are painful to plug into a local
agent: signed-in browser dances, token expirations, secrets scattered across
config files. This skill ships a local OAuth2 bridge that makes those servers
mouse-and-token-silent: connect once, then treat them as plain MCP servers.

## What it does

- Runs a tiny local proxy that handles the OAuth2 flow (authorize, token,
  refresh) for you — the agent just sees a normal, reachable MCP server.
- Ships a working recipe for the common cases (agent marketplaces with
  OAuth-gated servers) and the failure modes: expired refresh tokens,
  callback-port conflicts, config duplication between project and global.

## What you get

The bridge proxy (Node, no heavy dependencies), the install recipe, and the
hard-won troubleshooting notes — including the sane way to store tokens so a
crash doesn't wipe your keyrings.

## Honest limits

Designed for local, single-machine use with servers behind dynamic client
registration; enterprise SSO flows are out of scope.
