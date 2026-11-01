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

You need the LFG Alarm app on your phone, from [lfg.gm](https://lfg.gm), because that's where alarms ring. You also need a current OpenClaw: run `openclaw update` if you installed it a while ago.

1. Install the plugin:

   ```
   openclaw plugins install clawhub:@lfg/lfg-alarm
   ```

2. Add LFG Alarm:

   ```
   openclaw mcp add lfg-alarm --url https://mcp.lfg.gm --transport streamable-http --auth oauth --connect-timeout 30 --timeout 30 --no-probe
   ```

3. Sign in. Open the link it prints, sign in on lfg.gm and tap **Allow**:

   ```
   openclaw mcp login lfg-alarm
   ```

4. Restart OpenClaw, then ask for an alarm. Give it a minute to load LFG Alarm's tools first:

   ```
   openclaw gateway restart
   ```

Want OpenClaw to ask before it changes anything? Run `openclaw mcp configure lfg-alarm --approval prompt`. If nobody is there to answer, such as a scheduled job, the request is refused.

## What gets sent

- **Hosted service.** Every tool call goes to LFG Alarm's server at `mcp.lfg.gm`, signed in as you. That includes what you ask for: alarm titles, times, notes, links and the people you add.
- **Your model sees the results.** Reading your alarms or friends brings them into the chat, so they reach your model provider.
- **Tools can change things.** They make, change and delete alarms, and can ring every phone on an alarm you made.
- **The tool list comes from our server** when OpenClaw connects, so it can change without a new version of this plugin.
- **Your plan's limits apply**, as they do in the app.
- **Connected the LFG Alarm app in ChatGPT too?** OpenClaw may use that connection instead, which can be a different LFG account.

To disconnect, run `openclaw mcp unset lfg-alarm`, then remove OpenClaw under AI apps and keys in your LFG settings. Your alarms stay in your account.

## Support

- [Setup guide](https://lfg.gm/agents/openclaw)
- support@lfg.gm

LFG Alarm is not affiliated with OpenClaw.
