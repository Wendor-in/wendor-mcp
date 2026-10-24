# Connect Wendor to Gemini

Google does not run a public submission/browse directory for third-party MCP
servers in Gemini — there is no listing form to file. Gemini reaches MCP
servers through per-user connections:

## Gemini (web / app) — Connected Apps

1. Open gemini.google.com → **Settings → Connected Apps** (custom apps are
   available on personal Google accounts, 18+, where offered).
2. Add a custom app and paste the MCP server URL:
   `https://proddashboardapi.wendor.in/mcp`
3. Sign in with your Wendor account in the OAuth window and approve the
   read-only scopes. The app then appears in Gemini web and mobile.

Google asks for manual confirmation before any change made through a Gemini
custom app; the Wendor server is read-only in any case.

## Gemini CLI

```bash
gemini mcp add --transport http wendor https://proddashboardapi.wendor.in/mcp
```

Or add to `~/.gemini/settings.json`:

```json
{
  "mcpServers": {
    "wendor": { "httpUrl": "https://proddashboardapi.wendor.in/mcp" }
  }
}
```

Then run `gemini` and ask, e.g. "Which of my Wendor machines are offline?"

## Gemini Code Assist / Antigravity / other Google AI dev tools

Use the same `mcpServers` block above in the tool's MCP settings file.

## Discovery

Gemini users find this server through the Official MCP Registry and the
Smithery / Glama / PulseMCP listings published from this repository — the
canonical name everywhere is **Wendor** (`io.github.Wendor-in/wendor`).
