# Installing the LFG Alarm MCP server (for AI agents)

LFG Alarm is a hosted, remote MCP server. There is nothing to download, build or run locally.

- URL: `https://mcp.lfg.gm`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 with dynamic client registration. On first use the client opens a browser on lfg.gm, where the user signs in with their LFG Alarm account and taps **Allow**.
- Without OAuth: send `Authorization: Bearer <personal key>`, with a key the user makes in the LFG Alarm app's Settings.

## Steps

1. Add a remote MCP server named `lfg-alarm` with the URL `https://mcp.lfg.gm` and the Streamable HTTP transport. Config shape for most clients:

```json
{ "mcpServers": { "lfg-alarm": { "url": "https://mcp.lfg.gm" } } }
```

   In Cline: add it to `cline_mcp_settings.json` with the transport named, or Cline tries the older SSE transport and gets a 405:

```json
{ "mcpServers": { "lfg-alarm": { "type": "streamableHttp", "url": "https://mcp.lfg.gm" } } }
```

   Or open MCP Servers, choose **Remote Servers**, name it `lfg-alarm`, paste `https://mcp.lfg.gm`, pick **Streamable HTTP** and add it.

2. Connect. When the client asks, open the sign-in page and let the user sign in on lfg.gm. Do not ask the user for their password in chat.
3. Check it works by calling `list_my_alarms`. A list (or "no alarms yet") means it is connected.

## Requirements the user must meet

- An LFG Alarm account, and the LFG Alarm app installed and signed in on the phone that should ring (Google Play or the App Store). The AI makes alarms; the app rings them.

## Good first requests

- "Wake me at 7 on weekdays with something upbeat."
- "Ring me in 40 minutes, when this build should be done."

Setup guides for each app: https://lfg.gm/agents
