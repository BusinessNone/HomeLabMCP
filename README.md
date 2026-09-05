# Awesome HomeLab MCP [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated index of [Model Context Protocol](https://modelcontextprotocol.io) servers built for a self-hosted media, automation, and inference homelab.

Each server lives in its own repository. This repo is the index: no code, just pointers, short descriptions, and honest status.

## Contents

- [What counts as "in the list"](#what-counts-as-in-the-list)
- [Messaging bridges](#messaging-bridges)
- [Inventory and home operations](#inventory-and-home-operations)
- [In development](#in-development)
- [Prior art and credits](#prior-art-and-credits)
- [Status legend](#status-legend)
- [Contributing](#contributing)
- [License](#license)

## What counts as "in the list"

Three rules keep the list useful:

1. **One repo per server.** No monorepo, no vendored bundles. This index links out.
2. **Runs in a real homelab.** Every entry is deployed and used, not a proof of concept.
3. **Public-safe.** Repo history is scrubbed of hostnames, IPs, and API keys before listing. Servers that touch personal corpus data stay private regardless of how clean the code is.

## Messaging bridges

### signal-mcp

Bridges Signal messaging to MCP. Node plus better-sqlite3, stateful session mode, eight tools covering search, send, and contact resolution. Runs against a `signal-cli-rest-api` container.

**Status:** Mature, in active daily use.

### WhatsApp-MCP

Bridges WhatsApp to MCP through a [Baileys](https://github.com/WhiskeySockets/Baileys)-based container. Vendored from [loglux/whatsapp-mcp-stream](https://github.com/loglux/whatsapp-mcp-stream) with local build changes.

**Status:** Running and functional, less polished than signal-mcp.

### BlueBubbles-MCP

Bridges the [BlueBubbles](https://bluebubbles.app) REST API (iMessage on macOS) to MCP. Built on top of [metaember/bluebubbles-mcp](https://github.com/metaember/bluebubbles-mcp).

**Status:** Running, most tools live. A few tools are gated behind the BlueBubbles Private API, which is not enabled yet.

## Inventory and home operations

### homebox-shim

In-house MCP server for [Homebox](https://homebox.software) inventory management. Sixteen read and write tools, stateless streamable HTTP, zero npm dependencies. Written after the available third-party option proved read-only and outdated.

**Status:** Mature, 34 smoke assertions in the test suite. Cleanest candidate for the first public release: no personal-data entanglement.

## In development

### LazyLibrarian MCP

Exposes LazyLibrarian as a set of MCP tools. Currently at PRD stage.

**Status:** Not built. Listed here for visibility, not for use.

## Prior art and credits

- **homeboxmcp** — an earlier third-party Homebox MCP server. Not part of this collection; credited as prior art that `homebox-shim` was written to replace.
- **loglux/whatsapp-mcp-stream** and **metaember/bluebubbles-mcp** — upstream projects the WhatsApp and BlueBubbles bridges build on.

## Status legend

| Status | Meaning |
| --- | --- |
| Mature | Deployed, tested, used daily. Safe to depend on. |
| Running | Deployed and working. Rough edges, partial tool coverage, or thin tests. |
| Not built | Design exists, code does not. |

## Contributing

This is a personal index rather than an open catalog, so pull requests adding unrelated servers will be closed. Corrections, dead-link reports, and status updates are welcome via issues.

## License

[MIT](LICENSE)
