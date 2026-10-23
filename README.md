# Wendor MCP — Vending Machine Dashboard for AI Assistants

**Connect Claude, ChatGPT, Grok, Gemini, Cursor and any MCP client to your Wendor vending-machine business — sales, machines, inventory, refills, catalogue and support, in plain language.**

Wendor is a smart vending-machine platform. The Wendor MCP server is the official remote MCP endpoint for the Wendor Dashboard. Sign in once with your Wendor account (OAuth) and your AI assistant can answer questions about your fleet and business — no exports, no dashboard tabs, no copy-paste.

- **MCP endpoint:** `https://proddashboardapi.wendor.in/mcp`
- **Transport:** Streamable HTTP (remote, hosted — nothing to install)
- **Authentication:** OAuth 2.1 (sign in with your Wendor account) or a Wendor API key as `Authorization: Bearer <key>`
- **Access:** Read-only scopes — `profile`, `sales:read`, `machines:read`, `inventory:read`, `refills:read`, `catalog:read`, `support:read`, `finance:read`
- **Homepage:** https://wendor.ai

## What you can ask

- **Sales** — "What were yesterday's sales across my machines?" · "Which locations sold the most this week?"
- **Machines** — "Which machines are offline right now?" · "Show machine status for my Gurgaon sites."
- **Inventory** — "Which machines are running low on stock?" · "What's the inventory at location X?"
- **Refills** — "Which refills are due today?" · "What was refilled yesterday?"
- **Catalogue** — "What's in the current product catalogue and at what price?"
- **Support** — "What support tickets are open for my machines?"
- **Finance** — "Summarise collections for this month."

Every answer comes from your own Wendor account. You only ever see the machines, locations and data your Wendor role gives you in the dashboard — the MCP server enforces the same permissions.

## Connect in under a minute

### Claude
Claude.ai / Claude Desktop / Claude Code → **Settings → Connectors → Add custom connector** → paste the endpoint URL and sign in with Wendor when prompted.
Or in Claude Code:
```bash
claude mcp add --transport http wendor https://proddashboardapi.wendor.in/mcp
```

### ChatGPT
ChatGPT → **Settings → Connectors → Create** (Developer Mode) → name it `Wendor`, paste the endpoint URL, choose **OAuth**, and sign in.

### Grok
grok.com → **Connectors → New Connector → Custom** → paste the endpoint URL and complete Wendor sign-in.

### Gemini
Gemini (web) → **Settings → Connected Apps → custom app** → paste the endpoint URL and sign in.
Or Gemini CLI:
```bash
gemini mcp add --transport http wendor https://proddashboardapi.wendor.in/mcp
```

### Cursor / VS Code / any MCP client
```json
{
  "mcpServers": {
    "wendor": {
      "url": "https://proddashboardapi.wendor.in/mcp"
    }
  }
}
```

## Privacy & security

- OAuth 2.1 with PKCE; tokens are scoped read-only and revocable from your Wendor account at any time.
- No data is stored by the MCP server beyond what the Wendor Dashboard itself keeps.
- Privacy policy: https://wendor.ai/privacy — support: lakshit1001@gmail.com

## Listings

This server is published to the Official MCP Registry and mirrored to Smithery, Glama, PulseMCP and the Claude / ChatGPT / Grok directories from this repository (`server.json`, `glama.json`, `smithery.yaml`).

## License

This repository contains listing metadata and documentation for the hosted Wendor MCP server. The server itself is operated by Wendor (https://wendor.ai).
