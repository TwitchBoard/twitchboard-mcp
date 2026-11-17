# TwitchBoard MCP Server

Free tools for streamers, inside your AI assistant. [TwitchBoard](https://www.twitchboard.net/) is a set of free, no-sign-up browser tools for Twitch, YouTube, Kick, TikTok, Discord and OBS. This remote MCP server gives Claude, ChatGPT, Cursor, Gemini and any other MCP client the same answers the site gives: exact image sizes, name ideas that follow each platform's rules, ready-to-paste OBS widgets, bitrate settings and earnings estimates.

- **Server URL:** `https://www.twitchboard.net/mcp`
- **Transport:** Streamable HTTP
- **Auth:** none, no API key
- **Price:** free
- **Setup guide:** [twitchboard.net/mcp-server](https://www.twitchboard.net/mcp-server/)

Every tool is read-only. Results link back to the matching page on twitchboard.net, where you can do the same thing with a visual editor.

## Connect

### Claude (web, desktop and mobile)

Settings → Connectors → **Add custom connector**, paste `https://www.twitchboard.net/mcp` and save.

### Claude Code

```bash
claude mcp add --transport http twitchboard https://www.twitchboard.net/mcp
```

### Gemini CLI

```bash
gemini extensions install https://github.com/TwitchBoard/twitchboard-mcp
```

or, without the extension:

```bash
gemini mcp add --transport http twitchboard https://www.twitchboard.net/mcp
```

### Cursor

`~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "twitchboard": { "url": "https://www.twitchboard.net/mcp" }
  }
}
```

### VS Code

`.vscode/mcp.json`:

```json
{
  "servers": {
    "twitchboard": { "type": "http", "url": "https://www.twitchboard.net/mcp" }
  }
}
```

### Other clients

Add a remote (HTTP) MCP server with the URL `https://www.twitchboard.net/mcp`.

## Tools

| Tool | What it does | On the site |
|---|---|---|
| `search_tools` | Finds the free TwitchBoard tool for a task (resize an emote, make a banner, set up an overlay) and returns its link | [All tools](https://www.twitchboard.net/tools/) |
| `get_image_size` | Exact size, aspect ratio, file limits and tips for Twitch emotes, badges, panels and banners, YouTube banners and thumbnails, Discord emojis and stickers, Kick, TikTok and X images | [Streamer image sizes](https://www.twitchboard.net/sizes/) |
| `generate_names` | Name ideas that already follow the platform's username rules: Twitch, gamertags, Minecraft, Roblox, Discord, Discord servers, Fortnite, Valorant, Xbox, clans | [Twitch name generator](https://www.twitchboard.net/twitch/name-generator/) |
| `check_username` | Checks whether a Minecraft or Roblox username is taken | [Minecraft username checker](https://www.twitchboard.net/names/minecraft-username-checker/) |
| `create_obs_widget` | Ready-to-paste OBS browser source URL: countdown, stream timer, clock in any time zone, goal bar (manual or live TikTok followers) | [OBS countdown timer](https://www.twitchboard.net/obs/countdown-timer/) |
| `get_stream_settings` | OBS video and audio bitrate, resolution, keyframe interval and encoder preset for your platform and upload speed | [Bitrate calculator](https://www.twitchboard.net/obs/bitrate-calculator/) |
| `style_text` | Fancy Unicode text for Discord and Twitch chat, usernames and bios | [Discord font generator](https://www.twitchboard.net/discord/font-generator/) |
| `discord_timestamp` | Discord `<t:…>` codes that show a time in every reader's own time zone | [Discord timestamp generator](https://www.twitchboard.net/discord/timestamp-generator/) |
| `estimate_twitch_earnings` | Monthly Twitch income from subs, Prime, Bits and ads | [Twitch sub calculator](https://www.twitchboard.net/twitch/sub-calculator/) |
| `estimate_kick_earnings` | Kick sub income with the 95/5 split | [Kick sub calculator](https://www.twitchboard.net/kick/sub-calculator/) |
| `estimate_tiktok_earnings` | TikTok Creator Rewards, LIVE gifts and brand deals | [TikTok money calculator](https://www.twitchboard.net/tiktok/money-calculator/) |
| `convert_tiktok_coins` | TikTok coins to dollars, for viewers and creators | [TikTok coins calculator](https://www.twitchboard.net/tiktok/coins-calculator/) |

## Try asking

- "What size are Twitch emotes?"
- "Give me 10 cute Roblox usernames and check which ones are free."
- "Make an OBS countdown until Saturday 8 pm New York time."
- "What OBS bitrate should I use for Twitch at 1080p60 with 15 Mbps upload?"
- "Write 'Live today' in gothic letters for Discord."

## Privacy and limits

- Nothing you send is stored. Only the tool name and the client name are logged, to see which tools are useful.
- `check_username` sends the name you ask about to Minecraft's official lookup (or the PlayerDB mirror when Mojang doesn't answer) and to Roblox's official username check.
- Every tool call goes to `www.twitchboard.net`. The server needs no credentials and stores none.
- Limit: 120 requests per minute per IP address.

## Agent skill

[`skills/twitchboard/SKILL.md`](skills/twitchboard/SKILL.md) tells AI agents when and how to use the server.

## More free streamer tools

[Twitch emote resizer](https://www.twitchboard.net/twitch/emote-resizer/) · [Twitch panel maker](https://www.twitchboard.net/twitch/panel-maker/) · [Twitch chat overlay for OBS](https://www.twitchboard.net/obs/twitch-chat-overlay/) · [Stream Deck icon maker](https://www.twitchboard.net/graphics/stream-deck-icons/) · [Starting soon screen](https://www.twitchboard.net/graphics/starting-soon-screen/) · [Guides](https://www.twitchboard.net/guides/)

Also listed in the [Official MCP Registry](https://registry.modelcontextprotocol.io/) as `net.twitchboard/twitchboard`.

## License

MIT for the files in this repository. The server itself runs at twitchboard.net.
