# MCP Registry publishing

`server.json` describes the hosted Qreate endpoint for the official MCP Registry. Its name is `io.github.qreate-gg/qreate-mcp`.

This repository contains integration documentation, not Qreate's server source. No npm package or server code is published. Version `0.1.0` identifies this registry metadata release, not the deployed Qreate application version.

## Publish and update

The Publish Qreate to MCP Registry workflow uses GitHub Actions OIDC without a stored personal access token. It runs when `server.json` changes on `main`, or when an owner selects Run workflow in GitHub Actions.

For another registry release, update the version and any changed metadata in `server.json`. Registry versions are immutable. The workflow publishes metadata and checks the matching name, version and endpoint in the registry API.

The official publisher is pinned to v1.8.1 and its archive is verified against its release SHA-256 digest. Workflow permissions are limited to reading repository contents and obtaining an OIDC identity token.

A committed manifest alone does not establish registry inclusion. Confirm a successful publishing workflow and the returned registry entry. Inclusion is not client directory approval, automatic installation or a guarantee of search ranking.

## Sources

- [Remote server registration](https://modelcontextprotocol.io/registry/remote-servers)
- [GitHub Actions publishing](https://modelcontextprotocol.io/registry/github-actions)
- [Registry versioning](https://modelcontextprotocol.io/registry/versioning)
