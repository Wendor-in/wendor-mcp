# Files the dashboard backend must serve (one small deploy)

Serve these on **https://proddashboardapi.wendor.in** (the MCP host):

1. `/.well-known/glama.json` ← copy of `glama.json` in this folder.
   Claims the Glama connector listing for the Wendor account. Without it the
   connector that auto-appears after the Official Registry publish stays
   unclaimed and the awesome-remote-mcp-servers PR cannot merge (maintainer
   requires a Healthy, claimed connector badge).

2. `/.well-known/openai-apps-challenge` ← plain-text token, issued by the
   OpenAI plugin portal during the ChatGPT submission. Serve it EXACTLY as
   issued: HTTP 200, `text/plain`, no JSON wrapper, no extra whitespace list.

3. `/.well-known/mcp/server-card.json` ← static server card so Smithery and
   other scanners can list the server even when their probe cannot complete
   OAuth. Generate it from the live tool list once authenticated
   (name, endpoint, transport streamable-http, auth = OAuth 2.1).

Already live and correct (verified 2026-10-24):
- `/.well-known/oauth-authorization-server` (DCR + CIMD + PKCE S256)
- `/.well-known/oauth-protected-resource` and `/mcp` variant
- Unauthenticated POST /mcp → 401 with WWW-Authenticate Bearer challenge ✅
