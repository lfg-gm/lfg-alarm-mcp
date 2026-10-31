# LFG Alarm for Hermes Agent

Put a real alarm on your phone from Hermes. Ask for it in plain words, in any chat app Hermes is in, and your phone rings like an alarm clock. Share it and everyone who joined rings together.

## What you can ask

- "Wake me at 7 for my flight."
- "Set an alarm for 30 minutes before this Luma event, and make a link my friends can join."
- "Ring me when this creator goes live on Twitch."
- "Ring me if SOL drops 10%."
- "Make a surprise alarm for my team for Friday at 5."

## What's included

- **A skill** that teaches Hermes how to use LFG Alarm well.
- **The LFG Alarm MCP server** at `https://mcp.lfg.gm`, the same tools Claude and ChatGPT use. MCP is the standard way AI agents connect to outside tools.

There's no local code in this plugin: it's a pointer to the server and a skill.

## Get started

You need the LFG Alarm app on your phone, from [lfg.gm](https://lfg.gm). That's where alarms ring.

1. Install the plugin:

   ```
   hermes plugins install lfg-alarm --enable
   ```

2. Connect your LFG Alarm account. Hermes opens lfg.gm in your browser; sign in and click **Allow**:

   ```
   hermes mcp add lfg-alarm --url https://mcp.lfg.gm --auth oauth --connect-timeout 300
   ```

   On a machine with no browser, Hermes prints the sign-in link. Open it anywhere, then paste the address you land on back into Hermes.

3. Have Hermes ask you before it changes anything. The connect step replaces the plugin's own setting, so this puts it back:

   ```
   hermes config set mcp_servers.lfg-alarm.trust untrusted
   ```

4. Start a new session and ask for an alarm.

## What gets sent, and what stays safe

- **Hosted service.** Every tool call goes to LFG Alarm's server at `mcp.lfg.gm`, signed in as you. That includes what you ask for: alarm titles, times, notes, links and the people you add.
- **Your model sees the results.** Reading your alarms or friends brings them into the session, so they reach your model provider.
- **Tools can change things.** They make, change and delete alarms, and can ring every phone on an alarm you made. With step 3, Hermes asks you first. Reading never asks.
- **The tool list comes from our server** when Hermes connects, so it can change without a new version of this plugin.
- **Your plan's limits apply**, as they do in the app.
- **Hermes stores and refreshes your sign-in.** This plugin never sees it.

To disconnect, run `hermes mcp remove lfg-alarm`, then remove Hermes under AI apps and keys in your LFG settings. Your alarms stay in your account.

## Support

- [Setup guide](https://lfg.gm/agents/hermes-agent)
- support@lfg.gm

LFG Alarm is not affiliated with Nous Research.
