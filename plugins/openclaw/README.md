# LFG Alarm for OpenClaw

Put a real alarm on your phone from OpenClaw. Text it in plain words, and your phone rings like an alarm clock. Share it and everyone who joined rings together.

## What you can ask

- "Wake me at 7 for my flight."
- "Set an alarm for 30 minutes before this Luma event, and make a link my friends can join."
- "Ring me when this creator goes live on Twitch."
- "Ring me if SOL drops 10%."
- "Make a surprise alarm for my team for Friday at 5."

## What's included

- **A skill** that teaches OpenClaw how to use LFG Alarm well.
- **Setup steps** for the LFG Alarm MCP server at `https://mcp.lfg.gm`, the same tools Claude and ChatGPT use. MCP is the standard way AI agents connect to outside tools.

There's no code in this plugin. You add the server yourself in step 2, so it signs in as you.

## Get started

You need the LFG Alarm app on your phone, from [lfg.gm](https://lfg.gm). That's where alarms ring.

1. Install the plugin:

   ```
   openclaw plugins install clawhub:@lfg/lfg-alarm
   ```

2. Add the server and start sign-in. The longer time limits stop the first connection timing out:

   ```
   openclaw mcp set lfg-alarm '{"url":"https://mcp.lfg.gm","transport":"streamable-http","auth":"oauth","connectionTimeoutMs":30000,"requestTimeoutMs":30000}'
   openclaw mcp login lfg-alarm
   ```

   Open the link, sign in on lfg.gm and tap **Allow**. Your browser lands on a `127.0.0.1:8989` address, and the page may not load. Copy everything after `code=` and before `&state` from the address bar, then finish:

   ```
   openclaw mcp login lfg-alarm --code YOUR_CODE
   ```

3. Ask for an alarm.

## What gets sent

- **Hosted service.** Every tool call goes to LFG Alarm's server at `mcp.lfg.gm`, signed in as you. That includes what you ask for: alarm titles, times, notes, links and the people you add.
- **Your model sees the results.** Reading your alarms or friends brings them into the chat, so they reach your model provider.
- **Tools can change things.** They make, change and delete alarms, and can ring every phone on an alarm you made.
- **The tool list comes from our server** when OpenClaw connects, so it can change without a new version of this plugin.
- **Your plan's limits apply**, as they do in the app.

To disconnect, remove the server in OpenClaw, then remove it under AI apps and keys in your LFG settings. Your alarms stay in your account.

## Support

- [Setup guide](https://lfg.gm/agents/openclaw)
- support@lfg.gm

LFG Alarm is not affiliated with OpenClaw.
