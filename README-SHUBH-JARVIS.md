# SHUBH JARVIS — Stage 1 (Discord text controls)

This is a first, limited integration added to the supplied AFK bot project.

## Enabled now
- `/status` — owner-only Minecraft connection status and bot coordinates.
- `/say message:` — owner-only normal chat message from the Minecraft bot.
- `/jarvis-help` — lists the current Stage 1 commands.
- Discord commands are registered only in the configured Discord guild.
- Discord token and IDs are read from hosting environment variables.

## Not enabled yet
AI/Gemini replies, multiple personal JARVIS sessions, separate NPC accounts,
`/come`, `/follow`, building, crafting, mining, and player join/leave session logic.
These need later milestones and testing.

## Hosting setup
1. Upload this project ZIP to a Node.js service that allows persistent processes,
   outbound Discord gateway connections, and npm dependency installation.
2. Run `npm install` (this installs discord.js too), then use `npm start`.
3. Add these environment variables in the hosting panel:
   - `DISCORD_TOKEN` — bot token from Discord Developer Portal.
   - `DISCORD_CLIENT_ID` — Application ID.
   - `DISCORD_GUILD_ID` — your Discord server ID.
   - `DISCORD_OWNER_ID` — your own Discord user ID.
4. Invite the Discord application to your server with the `bot` and
   `applications.commands` scopes. Give only the minimum permissions needed
   to view the chosen channel and use application commands.
5. Restart the Node.js service. Use `/status` and `/say` in your Discord server.

## Important
- The included `settings.json` is sanitized with placeholders. **Do not use it to replace your currently working settings.json.** Keep your existing working Minecraft server/account settings and merge only the code/package changes unless you intentionally configure the placeholders.
- Never paste the bot token into chat, screenshots, source code, or a public GitHub repo.
- If a token is exposed, reset it immediately in the Developer Portal.
- Stage 1 commands are owner-only. Do not share the bot token with other players.
- Keep a backup of the currently working AFK bot before replacing any files.
- Hosting providers may restrict long-running Node.js apps or outbound gateway
  connections. Confirm that the FreeMCServer plan supports these before deployment.
