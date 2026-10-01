# Narrareach MCP

Official connection guide for the hosted [Narrareach](https://www.narrareach.com) MCP server.

Draft, schedule, and analyze content for **Substack, Medium, LinkedIn, X, Bluesky, and Threads**. Capabilities vary by platform and by your account's connected destinations.

This repository contains public connection documentation and registry metadata. The server runs on Narrareach infrastructure; its implementation is not distributed in this repository.

## Connect

- **Endpoint:** `https://www.narrareach.com/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth sign-in with your own Narrareach account
- **Requirements:** an eligible Narrareach account and connected platform accounts for platform-specific operations
- **Documentation:** https://www.narrareach.com/api-docs

In an MCP client that supports remote Streamable HTTP and OAuth, add the endpoint and complete the browser sign-in. Each connection acts on the authenticated account and its authorized team workspaces.

For Claude Code:

```sh
claude mcp add --transport http narrareach https://www.narrareach.com/mcp
```

Then use your client's OAuth authentication flow. Never place passwords or access tokens in a shared configuration file.

## Capabilities

The server exposes 33 tools. They cover draft and note editing, scheduling and cancellation, publishing readiness, authorized workspaces and writers, connected destinations, available analytics, saved inspiration, hashtag sets, and Substack reader activity.

Examples:

- List my drafts and suggest which one to edit next.
- Check the publishing readiness of my scheduled article.
- Show the available performance insights for my connected platforms.
- Preview a scheduling change before I approve it.

Read and write tools have different effects. Review the proposed content, destination and time before scheduling or modifying content. Existing scheduled items have provider-specific amendment restrictions.

## Listings

- [Official MCP Registry](https://registry.modelcontextprotocol.io/?q=narrareach): `io.github.iancarson/narrareach`
- [Glama](https://glama.ai/mcp/connectors/com.narrareach/narrareach)
- [Smithery](https://smithery.ai/servers/ian-akdi/narrareach)

## Health checks

An unauthenticated request receives HTTP 401 with OAuth discovery information. For authenticated tool discovery, authorize a dedicated test account using the directory's test profile. A 401 from an anonymous probe does not establish that the server is unavailable.

## Support and policies

- Support: ian.kiprono@narrareach.com
- [Privacy](https://www.narrareach.com/privacy)
- [Terms](https://www.narrareach.com/terms)
