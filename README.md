# Lemonvite plugin

Create, design and send digital invitations with RSVP tracking from Claude
Code or Codex. The plugin bundles the Lemonvite MCP connection
(`https://www.lemonvite.com/api/mcp`) and ships the skill that teaches the workflow: draft, review,
add guests, pay if needed, publish, track.

After installing the plugin, sign in with your Lemonvite account (OAuth,
no API key). Creating a draft never publishes, charges, or contacts anyone;
publishing costs one publish credit and delivers the invitations.

## Install the full plugin (recommended)

Clone this repository:

`git clone https://github.com/lemonberrylabs/lemonvite-plugin.git`

- **Claude Code:** run `claude --plugin-dir ./lemonvite-plugin`, then
  `/mcp` → `lemonvite` → Authenticate.
- **Codex:** open the cloned folder and ask Codex to install it as a local
  plugin using its plugin-creator skill. The bundle includes
  `.codex-plugin/plugin.json`, the skill and the MCP configuration.
  Enable the installed plugin, complete sign-in, and start a new thread.

Official directory approval is not required for this local setup.
[SETUP.md](./SETUP.md) covers authentication and troubleshooting.

## Skill only (separate MCP setup required)

`npx skills add lemonberrylabs/lemonvite-plugin --skill lemonvite-invitations`

This installs workflow instructions only. It does **not** register the MCP
server or attach tools to your session. Connect `https://www.lemonvite.com/api/mcp` in your
assistant and sign in separately, or install the full plugin above.

## Contents

- `.claude-plugin/plugin.json`: the Claude plugin manifest
- `.codex-plugin/plugin.json`: the Codex plugin manifest
- `.mcp.json`: the Lemonvite MCP server (remote, streamable HTTP, OAuth)
- `skills/lemonvite-invitations/SKILL.md`: the skill, identical to
  https://www.lemonvite.com/.well-known/agent-skills/lemonvite-invitations/SKILL.md

Generated from the lemonvite repository (`pnpm plugin:sync`). Edit it there, not here.

## License

The files in this repository are Apache-2.0 ([LICENSE](./LICENSE)).
That covers the plugin files only: using the Lemonvite service is governed by
https://www.lemonvite.com/terms, and the license grants no right to the Lemonvite name or marks.

## Links

- Website: https://www.lemonvite.com
- Privacy: https://www.lemonvite.com/privacy
- FAQ: https://www.lemonvite.com/faq
- Server card: https://www.lemonvite.com/api/mcp/server-card
