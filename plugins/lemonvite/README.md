# Lemonvite

Create, design and send digital invitations with RSVP tracking from a
conversation with Claude. Describe your event and Claude drafts the invitation
on Lemonvite, adds your guests (or invites people from your Lemonvite contact
list), publishes it to deliver the invitations by email, text message or
WhatsApp, and tells you who has responded.

## Use it

Connect the bundled Lemonvite connector and sign in with your Lemonvite
account (OAuth; there is no API key). Then ask, for example: "Draft an
invitation for Maya's 30th birthday on June 14 at The Garden Room", "Find
Alice in my Lemonvite contacts and invite her", or "Who hasn't replied yet?".
Creating a draft never publishes, charges, or contacts anyone. Publishing
delivers the invitations and uses account credits, and Claude asks you to
confirm before either.

## Data

The plugin contains a skill (instructions for Claude) and a reference to one
remote MCP server, `https://www.lemonvite.com/api/mcp`. It runs nothing on your computer. The
event details, guest names and contact details you give Claude are sent to
your Lemonvite account through that server, and Lemonvite sends the
invitations. Lemonvite's privacy policy: https://www.lemonvite.com/privacy. Terms: https://www.lemonvite.com/terms.
[SETUP.md](./SETUP.md) covers sign-in and troubleshooting.
