# Lemonvite plugin

Create, design and send digital invitations with RSVP tracking from Claude
Code or Cowork. The plugin connects Claude to the Lemonvite MCP server
(`https://www.lemonvite.com/api/mcp`) and ships the skill that teaches the workflow: draft, review,
add guests, pay if needed, publish, track.

You sign in with your Lemonvite account when Claude first uses a tool (OAuth,
no API key). Creating a draft never publishes, charges, or contacts anyone;
publishing costs one publish credit and delivers the invitations.

## Install

- Claude Code, from the official marketplace once listed:
  `/plugin install lemonvite@claude-plugins-official`
- Claude Code, from this repository:
  `git clone https://github.com/lemonberrylabs/lemonvite-plugin.git` then `claude --plugin-dir ./lemonvite-plugin`
- Skill only (skills.sh): `npx skills add lemonberrylabs/lemonvite-plugin`

[SETUP.md](./SETUP.md) has the connection steps.

## Contents

- `.claude-plugin/plugin.json`: the plugin manifest
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
