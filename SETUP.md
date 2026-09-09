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

## Gemini CLI

Run in your terminal (adds Lemonvite to your user configuration):

```sh
gemini mcp add --transport http --scope user lemonvite https://www.lemonvite.com/api/mcp
gemini
```

Inside Gemini CLI, run `/mcp auth lemonvite`. Sign in to Lemonvite in the
browser and approve access, then run `/mcp list` to check the connection.
[Official Gemini CLI instructions](https://geminicli.com/docs/tools/mcp-server/).

## GitHub Copilot CLI

Run in your terminal:

```sh
copilot mcp add --transport http lemonvite https://www.lemonvite.com/api/mcp
copilot
```

Inside Copilot CLI, run `/mcp auth lemonvite` to sign in through your browser,
then `/mcp list` to check the connection. This is for the terminal CLI;
Copilot's cloud agent has different authentication support.
[Add MCP servers](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-mcp-servers)
· [OAuth authentication](https://docs.github.com/en/copilot/reference/copilot-cli-reference/cli-command-reference#oauth-re-authentication).

## OpenCode v2

Merge this entry into your project's `opencode.jsonc`. Keep existing settings
and other servers in place:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "servers": {
      "lemonvite": {
        "type": "remote",
        "url": "https://www.lemonvite.com/api/mcp"
      }
    }
  }
}
```

Open OpenCode's MCP management interface, select Lemonvite and authenticate
when prompted. Complete sign-in in your browser. OAuth is enabled by default
for remote servers. The nested `mcp.servers` format above is for **OpenCode v2**;
check your version before changing an older configuration.
[Official OpenCode v2 instructions](https://opencode.ai/v2/docs/mcp-servers).

## Other MCP clients

Add a remote **Streamable HTTP** server named `lemonvite` with URL
`https://www.lemonvite.com/api/mcp`. Choose OAuth and complete Lemonvite sign-in. The client must
support remote OAuth discovery and dynamic client registration or client
metadata documents. A client limited to API keys will not work with this setup.

## Verify / troubleshoot

Check the connection with a read-only call, for example "list my Lemonvite
invitations" (`lemonvite_list_invitations`).

If tools are missing, check that the **plugin or MCP connection** is enabled,
rather than only its skill. Complete authentication and retry in a new session. Installing
with `npx skills add` alone never registers the MCP connection.

To disconnect in Claude Code: `/mcp` → `lemonvite` → Clear authentication, or
Settings → Connected assistants on https://www.lemonvite.com, which revokes the tokens
server-side.

Generated from the lemonvite repository (`pnpm plugin:sync`). Edit it there, not here.
