# Qreate MCP: build and run Discord communities with your AI

**Tell your AI what your Discord community needs. Qreate turns the idea into a plan you can review and launch.**

Connect Claude or ChatGPT to [Qreate](https://qreate.gg), inspect your server, and turn requests into coordinated changes across channels, roles and module settings. Build onboarding, configure support, prepare automations and draft announcements through one connected workflow.

[Get started with Qreate](https://qreate.gg) · [Documentation](https://docs.qreate.gg) · [Discord support](https://discord.gg/qreate)

## Connect Qreate for me

Send your AI assistant this repository link with:

> Connect Qreate using https://github.com/qreate-gg/qreate-mcp/blob/main/INSTALL.md. Configure it for this client if you can, guide me through OAuth, then show my accessible Discord servers. Do not change my server during setup.

An agent with access to your client configuration can prepare the connection. You complete sign-in and consent; clients without configuration access need a short manual setup.

**[Add to Cursor](https://cursor.com/link/mcp/install?name=qreate&config=eyJ1cmwiOiJodHRwczovL21jcC5xcmVhdGUuZ2cvbWNwIn0%3D)** · **[Connect Claude](#claude-web-and-desktop)** · **[Connect ChatGPT](#chatgpt)** · **[Agent installation guide](INSTALL.md)**

The Cursor link opens an installation prompt. Claude and ChatGPT links lead to their setup instructions, not automatic installers. All connections use OAuth.

## One connection, connected server workflows

An idea often involves several parts of a Discord server. Qreate reads what already exists and prepares the work together, so your assistant can move from a request to a concrete, reviewable setup.

- **Start from your actual server.** Inspect channels, roles and current module configuration.
- **Build across modules.** The current capability catalogue contains 36 modules, including welcome, verification, tickets, role menus, leveling, giveaways and automations. Available changes are determined by Qreate's planner and server permissions.
- **Use ready-made foundations.** Discover server templates and preview their setup.
- **Review before launch.** Qreate executes the stored plan you approve.
- **Publish deliberately.** Preview a standalone announcement, then approve the exact draft.
- **Keep working with context.** Resume questions and inspect recent planning runs.

This is a hosted Discord MCP integration. This repository contains connection documentation and a client configuration example. The Qreate service runs at:

```text
https://mcp.qreate.gg/mcp
```

No repository clone or local server installation is needed to use the hosted service. Qreate's application source and server implementation are not distributed here.

## Continuous updates and early access

Qreate MCP is actively developed and continuously updated. Improvements to the hosted service do not require reinstalling a local server. Refresh your client's connector to discover changes to the tool catalogue.

**[Qreate MCP Preview](https://preview.mcp.qreate.gg) · Coming soon**

The planned Preview channel will introduce new capabilities while they are still being tested. This address is reserved in this documentation for the upcoming preview; it is not a verified connection endpoint. Use the main MCP endpoint above for the documented integration.

## Connect

You need a Qreate account, a Discord server you administer with Qreate connected, and an AI client that supports remote MCP and OAuth. Client and workspace policies may restrict custom connections.

### Claude Code

With Claude Code installed, add the hosted server using its documented JSON configuration command:

```sh
claude mcp add-json qreate '{"type":"http","url":"https://mcp.qreate.gg/mcp"}'
```

Open Claude Code, run `/mcp`, select Qreate and complete the OAuth sign-in. Then ask:

> Show the Discord servers I can manage with Qreate.

The equivalent configuration is in [examples/claude-code.mcp.json](examples/claude-code.mcp.json). Merge its entry into your project's `.mcp.json` if you prefer project configuration.

[Official Claude Code MCP instructions](https://code.claude.com/docs/en/mcp)

### Claude web and Desktop

1. Open **Customize → Connectors → Add → Custom → Web**.
2. Name the connector **Qreate** and enter the endpoint above.
3. Review the detected authentication settings and select sign-in.
4. If Claude offers an OAuth client choice, use **Register automatically** for Qreate's documented client-registration flow.
5. Add the connector and complete Qreate's consent screen.
6. Enable Qreate in your conversation and ask it to list your servers.

Remote connectors use Claude's connector interface. This guide does not require editing `claude_desktop_config.json`.

[Official Claude connector instructions](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities)

### ChatGPT

For the current Plugins interface:

1. Open [ChatGPT Plugins](https://chatgpt.com/plugins).
2. Select **+ → Add custom MCP server**.
3. Enter **Qreate**, a description, and the endpoint above under Connection.
4. Configure **OAuth**, complete sign-in and review the requested access.
5. Select **Create as a plugin** and review the discovered tools.
6. Install the plugin, start a new conversation, type `@` and select **Qreate**. Use Work where your interface requires it.

If custom MCP creation is restricted, check your account's developer access and workspace policy. Qreate's [connection guide](https://docs.qreate.gg/mcp) documents enabling Developer mode under **Settings → Security and login** for its Work flow. Interfaces with an **Apps** menu use the setup route documented for that interface rather than the Plugins menu.

[Official ChatGPT connection instructions](https://developers.openai.com/plugins/deploy/connect-chatgpt)

**Verification note:** these setup steps follow official client documentation and Qreate's public guide. The tool catalogue and capabilities were inspected through an existing authenticated Qreate connection on 13 October 2026. Fresh sign-in in each client has not been tested as part of this documentation review.

## Try an idea

These are example requests, not preconfigured templates or guaranteed one-step outcomes. Qreate checks what your server and the current planner can support.

> Read my server and show which Qreate modules are configured.

> Plan a welcome flow in my welcome channel using the roles already on the server. Show every change before applying it.

> Prepare a support setup with a ticket module and suitable staff roles. Ask me for any missing details.

> Plan an automation that posts a message when my chosen trigger occurs. Let me review the trigger and actions.

> Show the available server templates and preview the one that best fits a gaming community.

> Draft an announcement for my announcements channel with a link to our rules. Show me the complete message before publishing.

See [more examples and execution flows](docs/examples.md).

## Supported MCP tools

The currently exposed catalogue contains **20 tools**:

| Workflow | Tools |
| :--- | :--- |
| Discover access and capabilities | `qreate_list_servers`, `qreate_get_capabilities` |
| Read server configuration | `qreate_get_server`, `qreate_get_server_context`, `qreate_get_channels`, `qreate_get_roles`, `qreate_get_modules`, `qreate_get_module_config` |
| Plan, clarify and apply | `qreate_plan_setup`, `qreate_preview_plan`, `qreate_apply_plan`, `qreate_answer_plan_question` |
| Inspect ongoing work | `qreate_get_run`, `qreate_list_runs` |
| Discover and use templates | `qreate_get_recipes`, `qreate_plan_recipe`, `qreate_apply_recipe` |
| Draft and publish a message | `qreate_preview_message`, `qreate_publish_message` |
| Reverse an applied change batch | `qreate_undo_changes` |

See the [tool reference](docs/tools.md) for each tool's purpose and approval requirements. Clients may add a namespace prefix to tool names. Refresh your connector if its catalogue is older.

## OAuth and access

The client sends you to Qreate to sign in and review a consent screen identifying the client and the Discord servers it can reach. You explicitly connect the client. Qreate verifies server administration access on every request.

Use the client's OAuth flow; do not put a Discord bot token, account password or copied access token into this repository. Only authorize a client whose connection request you recognize.

To revoke access, open **Account** in Qreate and disconnect the connected client. Revocation stops access; changes already applied to Discord remain.

## Review and execution boundaries

For setup, the flow is **read → plan → preview → approve → apply**. A plan can configure modules, rules, entities and server scaffolding. Its approval refers to a stored plan; the client does not provide replacement actions when applying it. Stale plans are refused.

Messages use a separate **draft → preview → approve → publish** flow. A setup plan never posts a standalone message. Publishing the same draft again returns the existing receipt instead of posting twice.

Connected AI clients cannot delete channels, roles, messages or records; ban, kick or time out members; or change Qreate's own authority. These boundaries are specific to MCP. Configuring the moderation module does not grant the client member-moderation tools.

## Troubleshooting

- **A server is missing:** check that you administer it and have connected Qreate.
- **A plan is stale:** request a fresh plan against the current server.
- **Tools are missing:** refresh the connection and start a new conversation.
- **An action fails:** review Qreate's result and the relevant Discord channel permissions and role hierarchy.
- **Message delivery is uncertain:** check the Discord channel before requesting another publish.
- **Connection setup fails:** use the official client guide above and [Qreate support](https://discord.gg/qreate). A normal browser visit to the endpoint is not an MCP connection test.

## Learn more

- [Qreate](https://qreate.gg)
- [Qreate documentation](https://docs.qreate.gg)
- [MCP integration guide](https://docs.qreate.gg/mcp)
- [Qreate blog](https://blog.qreate.gg)
- [Discord support](https://discord.gg/qreate)

Qreate, Claude and ChatGPT are named to identify the service and compatible client setup routes. This repository does not imply endorsement or directory approval by Anthropic or OpenAI.
