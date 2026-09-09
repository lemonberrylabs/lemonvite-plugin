# Lemonvite plugin

[![smithery badge](https://smithery.ai/badge/lemonvite/lemonvite)](https://smithery.ai/servers/lemonvite/lemonvite)

Create, design and send digital invitations with RSVP tracking from Claude
Code or Codex. The plugin bundles the Lemonvite MCP connection
(`https://www.lemonvite.com/api/mcp`) and ships the skill that teaches the workflow: draft, review,
add guests, pay if needed, publish, track.

After installing the plugin, sign in with your Lemonvite account (OAuth,
no API key). Creating a draft never publishes, charges, or contacts anyone;
publishing costs one publish credit and delivers the invitations.

## Install the full plugin (recommended)

### Codex

Run in your terminal:

```sh
codex plugin marketplace add lemonberrylabs/lemonvite-plugin
codex plugin add lemonvite@lemonvite
```

Restart Codex, enable Lemonvite in Plugins, complete sign-in, and start a new
thread. No manual MCP URL setup is needed.

### Claude Code

Run inside Claude Code:

```text
/plugin marketplace add lemonberrylabs/lemonvite-plugin
/plugin install lemonvite@lemonvite
```

Reload plugins if prompted, then use `/mcp` → `lemonvite` → Authenticate.
For local development: clone this repo and run
`claude --plugin-dir ./lemonvite-plugin/plugins/lemonvite`.

Official directory approval is not required for these marketplace installs.
[SETUP.md](./SETUP.md) covers authentication and troubleshooting.

## Skill only (separate MCP setup required)

`npx skills add lemonberrylabs/lemonvite-plugin --skill lemonvite-invitations`

This installs workflow instructions only. It does **not** register the MCP
server or attach tools to your session. Connect `https://www.lemonvite.com/api/mcp` in your
assistant and sign in separately, or install the full plugin above.

## Contents

- `.agents/plugins/marketplace.json`: Codex marketplace
- `.claude-plugin/marketplace.json`: Claude marketplace
- `plugins/lemonvite/`: self-contained plugin bundle with both manifests,
  `.mcp.json`, setup instructions and license
- `plugins/lemonvite/skills/lemonvite-invitations/SKILL.md`: skill, identical to
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
