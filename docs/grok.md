# Connect Wendor to Grok

## Grok (grok.com) — custom connector

1. Go to grok.com → **Connectors → New Connector → Custom**.
2. Paste the MCP server URL: `https://proddashboardapi.wendor.in/mcp`
3. Complete the Wendor OAuth sign-in. Grok discovers the Wendor tools
   automatically; enable the connector per chat from the **+ → Connectors**
   menu.

On Grok Business / Enterprise, an admin adds the connector once in
console.x.ai (Grok Business → Connectors → Add Connector → Other); each user
then signs in with their own Wendor account.

## Grok Build — plugin marketplace

This repository is also submitted as a plugin to the official xAI plugin
marketplace (`xai-org/plugin-marketplace`) as a remote-source entry pinned to
a commit of this repo, with the plugin manifest at `.grok-plugin/plugin.json`.
Once merged, Grok Build users can install **wendor** from the marketplace.

## Grok API

xAI's API accepts remote MCP servers — pass the same URL
(`https://proddashboardapi.wendor.in/mcp`) as a remote MCP tool and scope
`allowed_tools` to the read-only Wendor tools you want the model to use.
