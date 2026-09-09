# Connecting Lemonvite

The plugin declares one remote MCP server, `lemonvite`, at
`https://www.lemonvite.com/api/mcp`. It uses OAuth 2.1; there is no API key to enter.

## Claude Code

1. Enable the plugin. Claude Code registers the server from `.mcp.json`.
2. Run `/mcp`, pick `lemonvite`, and choose Authenticate. A browser tab
   opens the Lemonvite sign-in and consent page.
3. Sign in with Google, a magic link or a phone code. A Lemonvite account
   needs an email address or phone number; the sign-in page creates one if
   needed.
4. Approve the consent screen. Claude Code stores the tokens; nothing else to
   configure.

## Codex

Run `codex plugin marketplace add lemonberrylabs/lemonvite-plugin`, then
`codex plugin add lemonvite@lemonvite`. Restart Codex and open
Lemonvite in Plugins to complete sign-in. Start a new thread
after installation so the skill and MCP tools are loaded together.

## Verify / troubleshoot

Check the connection with a read-only call, for example "list my Lemonvite
invitations" (`lemonvite_list_invitations`).

If tools are missing, check that the **plugin** is enabled, rather than only
its skill. Complete authentication and retry in a new session. Installing
with `npx skills add` alone never registers the MCP connection.

To disconnect in Claude Code: `/mcp` → `lemonvite` → Clear authentication, or
Settings → Connected assistants on https://www.lemonvite.com, which revokes the tokens
server-side.

Generated from the lemonvite repository (`pnpm plugin:sync`). Edit it there, not here.
