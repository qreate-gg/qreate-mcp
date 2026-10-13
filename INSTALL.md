# Connect Qreate

For users and AI agents asked to connect Qreate. This file is an installation guide, not permission to change a Discord server.

## Connection facts

| Field | Value |
| :--- | :--- |
| Name | Qreate |
| Configuration key | `qreate` |
| Hosted endpoint | `https://mcp.qreate.gg/mcp` |
| Transport | Streamable HTTP |
| Authentication | OAuth through Qreate |
| Prerequisites | Qreate account and a Discord server you administer with Qreate connected |

No clone, npm package, local MCP process or Discord bot token is required.

## Agent setup procedure

1. Identify the client from the current environment. If unclear, ask which client to configure.
2. Inspect its existing MCP configuration if accessible. Preserve other entries and reuse an existing Qreate connection rather than duplicating it.
3. Use the matching route below. If you cannot change client settings, give the user the exact manual steps; reading this file alone does not connect MCP.
4. Hand OAuth sign-in and consent to the user. Never request passwords or copied tokens in chat.
5. After authentication, discover tools and call `qreate_list_servers`, then `qreate_get_capabilities`. Report that connection worked only when the calls succeed. Do not publish, apply plans or modify Discord during this setup check.

## Claude Code

For a new connection, use Claude Code's supported command:

```sh
claude mcp add-json qreate '{"type":"http","url":"https://mcp.qreate.gg/mcp"}'
```

This command uses the default local/project context. If project configuration is desired, merge the Qreate entry from [examples/claude-code.mcp.json](examples/claude-code.mcp.json) into `.mcp.json`; do not overwrite other entries.

Open Claude Code, run `/mcp`, select Qreate and complete OAuth. MCP tools must be discovered before you claim the connection is ready.

## Cursor

[Add Qreate to Cursor](https://cursor.com/link/mcp/install?name=qreate&config=eyJ1cmwiOiJodHRwczovL21jcC5xcmVhdGUuZ2cvbWNwIn0%3D)

Accept Cursor's installation prompt, complete OAuth and use Qreate in your conversation. Alternatively merge [examples/cursor.mcp.json](examples/cursor.mcp.json) into Cursor's MCP configuration, preserving existing entries.

The link follows Cursor's documented installation format. Its encoded payload contains only the endpoint; it does not contain credentials. A fresh Cursor OAuth session has not been tested in this repository's documentation review.

## Claude web and Desktop

Open **Customize → Connectors → Add → Custom → Web**. Enter **Qreate** and the hosted endpoint. Select sign-in, review OAuth settings and complete consent. If an OAuth client choice appears, Qreate's public client-registration flow corresponds to **Register automatically**. Enable the connector in your conversation.

## ChatGPT

Open [ChatGPT Plugins](https://chatgpt.com/plugins), choose **+ → Add custom MCP server**, enter **Qreate** and the hosted endpoint, select OAuth and complete authorization. Create the plugin, review its tools and install it. In a new conversation, type `@` and select Qreate. Account and workspace restrictions apply.

See [the complete connection guide](README.md#connect) if your interface differs.

## First request

> Show the Discord servers I can manage with Qreate and explain what this connection can do. Do not change anything yet.

## Official references

- [Claude Code MCP](https://code.claude.com/docs/en/mcp)
- [Claude connectors](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities)
- [Cursor MCP install links](https://prod.cursor.com/docs/mcp/install-links)
- [ChatGPT MCP connection](https://developers.openai.com/plugins/deploy/connect-chatgpt)
- [Qreate connection and revocation](https://docs.qreate.gg/mcp)
