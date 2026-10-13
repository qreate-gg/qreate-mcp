# Discord MCP use cases for Claude, ChatGPT and Cursor

Connect with [the installation guide](../INSTALL.md), then use one of these prompts. These are requests to Qreate's planner, not promises of a predefined result. Available changes depend on the server, permissions and current planner.

## Build Discord onboarding with your AI

Copy this request:

> Read my server's current channels, roles and module settings. Plan a welcoming onboarding flow using my existing welcome channel and Member role. Suggest the welcome and verification settings that fit this server, ask for missing details, and show every proposed change. Wait for my approval before applying.

Qreate reads server context, prepares the setup and asks questions where necessary. Review the stored plan, then explicitly approve the version you want applied.

Useful for community owners who want connected onboarding rather than separate settings chosen without server context.

## Prepare a Discord support workflow

Copy this request:

> Read my server and current ticket module configuration. Help me prepare a ticket support setup using existing staff roles. Ask me about routing and permissions where needed, then show what your planner can configure before applying anything.

The resulting plan determines what is supported. Ticket-module setup is different from reading private ticket conversations: the exposed catalogue does not provide general ticket-transcript tools.

Useful for Discord communities bringing support configuration into their AI-assisted setup process.

## Plan Discord automations

Copy this request:

> Help me plan an automation for this server. I want a message in my event channel when the trigger I choose occurs. Check the existing configuration, ask me to specify a supported trigger, and preview the trigger, conditions and actions. Do not apply until I approve.

Creating an automation uses the setup planning flow. A standalone announcement now uses message drafting and publishing instead.

Useful for recurring community operations that need a clear trigger and reviewable actions.

## Draft a Discord announcement

Copy this request:

> Find my announcements channel and draft a message welcoming members to our new event. Add a link button to our rules. Show the entire message and wait for my approval before publishing it.

Qreate returns a draft, then publishes the exact approved draft. The Announcements module must be enabled. Put notifying mentions in message content rather than an embed.

## Start with a server template

Copy this request:

> Show the ready-made Qreate server templates available now. Help me choose one for my community and preview exactly which channels, roles and module settings it would create.

Use templates returned by live discovery; do not invent template names. Approve the preview before applying.

## First successful connection

Copy this request:

> List the servers I administer through Qreate and read the connection's capabilities. Do not change anything.

This is a read-only way to confirm setup. Share installation feedback through [GitHub Issues](https://github.com/qreate-gg/qreate-mcp/issues) or [Qreate support](https://discord.gg/qreate). If the integration is useful, a GitHub star helps other community owners discover it.
