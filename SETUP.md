# Connecting Lemonvite

The plugin declares one remote MCP server, `lemonvite`, at
`https://www.lemonvite.com/api/mcp`. It uses OAuth 2.1; there is no API key to enter.

1. Enable the plugin. Claude Code registers the server from `.mcp.json`.
2. Run `/mcp`, pick `lemonvite`, and choose Authenticate. A browser tab
   opens the Lemonvite sign-in and consent page.
3. Sign in with Google, a magic link or a phone code. A Lemonvite account
   needs an email address or phone number; the sign-in page creates one if
   needed.
4. Approve the consent screen. Claude Code stores the tokens; nothing else to
   configure.

Check the connection with a read-only call, for example "list my Lemonvite
invitations" (`lemonvite_list_invitations`).

To disconnect: `/mcp` → `lemonvite` → Clear authentication, or
Settings → Connected assistants on https://www.lemonvite.com, which revokes the tokens
server-side.

Generated from the lemonvite repository (`pnpm plugin:sync`). Edit it there, not here.
