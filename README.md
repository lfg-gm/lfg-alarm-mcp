<p align="center"><img src="logo.png" width="96" alt="LFG Alarm"></p>

# LFG Alarm MCP server

Let your AI ring a real alarm on any phone or laptop, at any time or for any moment online.

[LFG Alarm](https://lfg.gm) is a social alarm clock for iPhone and Android. Rocco, LFG's agent, monitors the web and wakes you, and your friends, when it matters: at a time, when a token moves, when someone posts or goes live, when a trader or a wallet trades, before an event, or when anything online calls a private link. This server lets any AI app that speaks MCP make and manage those alarms for you, in plain words.

[![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=lfg-alarm&config=eyJ1cmwiOiJodHRwczovL21jcC5sZmcuZ20ifQ%3D%3D) [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_LFG_Alarm-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=lfg-alarm&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.lfg.gm%22%7D)

- **Server:** `https://mcp.lfg.gm`
- **Transport:** Streamable HTTP (remote; nothing to install)
- **Sign-in:** OAuth. The first time, a page on lfg.gm opens; sign in with your LFG Alarm account and tap **Allow**. For tools without sign-in, use a personal key from the app's Settings as a `Bearer` header.
- **Registry name:** `gm.lfg/alarm` in the [official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=gm.lfg/alarm)
- **Full setup guides:** [lfg.gm/agents](https://lfg.gm/agents)

You need the LFG Alarm app on your phone ([Google Play](https://play.google.com/store/apps/details?id=gm.lfg.app) or the [App Store](https://apps.apple.com/app/id6821089085)), signed in. Your AI makes the alarms; the app rings them.

## Connect it

### Claude (claude.ai and the desktop app)

**Settings** > **Connectors** > **Add custom connector**, name it LFG Alarm, paste `https://mcp.lfg.gm`, then sign in. [Guide](https://lfg.gm/agents/claude)

### ChatGPT

Add LFG Alarm as an app with the address `https://mcp.lfg.gm`, then sign in. [Guide](https://lfg.gm/agents/chatgpt)

### Claude Code

```bash
claude mcp add --transport http --scope user lfg-alarm https://mcp.lfg.gm
```

### Cursor

Add to `~/.cursor/mcp.json`, then turn it on under **Customize** > **MCPs** and sign in. [Guide](https://lfg.gm/agents/cursor)

```json
{ "mcpServers": { "lfg-alarm": { "url": "https://mcp.lfg.gm" } } }
```

### VS Code (GitHub Copilot)

Run **MCP: Add Server**, choose **HTTP**, paste `https://mcp.lfg.gm`, or add to `.vscode/mcp.json`: [Guide](https://lfg.gm/agents/vs-code)

```json
{ "servers": { "lfg-alarm": { "type": "http", "url": "https://mcp.lfg.gm" } } }
```

### Windsurf (Devin Desktop)

Add to `~/.config/devin/mcp_config.json` (Windows: `%APPDATA%\devin\mcp_config.json`): [Guide](https://lfg.gm/agents/windsurf)

```json
{ "mcpServers": { "lfg-alarm": { "url": "https://mcp.lfg.gm" } } }
```

### Gemini CLI

Install this repo as an extension:

```bash
gemini extensions install https://github.com/lfg-gm/lfg-alarm-mcp
```

Or add the server yourself, then run `/mcp auth lfg-alarm` to sign in: [Guide](https://lfg.gm/agents/gemini-cli)

```bash
gemini mcp add --transport http -s user lfg-alarm https://mcp.lfg.gm
```

### Anything else

Any MCP client that supports remote Streamable HTTP servers works with `https://mcp.lfg.gm`. Clients that cannot sign in by OAuth can send `Authorization: Bearer <personal key>`. More apps: [lfg.gm/agents](https://lfg.gm/agents).

## Try it

- "Wake me at 7 on weekdays with something upbeat."
- "Ring me in 40 minutes, when this migration should be done."
- "Set an alarm for when SOL moves 10%, and add my friend [username]."
- "Ring me before this Luma event starts: [link]."
- "Make a friends alarm for Friday at 4pm called Release and add [username] and [username]."

## What it can do

| Tool | What it does |
|---|---|
| `set_time_alarm` | Set a time alarm, once or on repeat days |
| `set_price_alarm` | Set a price alarm for a token (a target price or a percent move) |
| `find_token` | Find a token to watch |
| `set_post_alarm` | Ring when an X account posts something, or a Twitch or YouTube channel goes live or posts |
| `set_trader_alarm` | Ring when a trader, a token's traders or a wallet buys or sells (Solana and EVM chains) |
| `set_event_alarm` | Ring before an event from its Luma or Partiful link |
| `set_webhook_alarm` | Ring when anything calls a private web address |
| `update_alarm` | Change an alarm: time, title, sound, wallpaper, note, snooze, who is on it |
| `turn_alarm_on_off` | Turn an alarm on or off |
| `delete_alarm` | Delete an alarm |
| `list_my_alarms` | List my alarms |
| `show_alarm` | Show an alarm |
| `search_library` | Search LFG's library of 500+ sounds and drawn wallpapers |
| `search_gifs` | Search GIFs (from KLIPY) |
| `set_gif` | Put a GIF on an alarm |
| `set_media` | Put a library item or an upload on an alarm |
| `add_media_from_url` | Add a picture, video, song or voiceover from a link |
| `add_media_file` | Add a picture, video, song or voiceover file |
| `get_upload_link` | Get a one-time page to add a file from your device |
| `list_my_media` | List my uploads |
| `list_friends` | List my friends and groups |
| `list_riders` | See who is riding an alarm |
| `list_join_requests` | See who asked to join |
| `answer_join_request` | Let someone in, or not |
| `get_invite_card` | Get my invite link and invite card |
| `use_invite_code` | Use a friend's invite code |
| `open_link` | Open an LFG alarm link |
| `join_alarm` | Join an alarm from its link |
| `browse_discover` | Browse public alarms |
| `read_comments` | Read an alarm's comments |
| `post_comment` | Comment on an alarm |
| `heart_alarm` | Heart an alarm |
| `get_wake_board` | Get the wake board: who got up, and how fast |

In Claude and ChatGPT, alarms also show as an interactive card (MCP Apps) to preview the ring and change the sound or wallpaper.

## How alarms ring

Time and event alarms ring as real alarms on both iPhone and Android. Post, price, trader and webhook alarms ring full screen on Android and as a time-sensitive alert on iPhone. Alarms also ring in an open LFG Alarm tab on a laptop.

## Plans

Some alarm types and limits depend on the account's plan. For plans and pricing, go to [lfg.gm](https://lfg.gm).

## Support and policies

- Help: [lfg.gm/support](https://lfg.gm/support), or email support@lfg.gm
- Privacy and terms: [lfg.gm/legal](https://lfg.gm/legal)
- Developers: [lfg.gm/developers](https://lfg.gm/developers)

This repository holds the setup guide and client config for the hosted server. The server itself runs at `mcp.lfg.gm`.
