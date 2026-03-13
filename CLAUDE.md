# Trunk MCP Server

## What This Repo Is

Public-facing repo for the **Trunk.io MCP Server** (`https://mcp.trunk.io/mcp`). This repo serves two purposes:

1. **Public repo** — the root files (`README.md`, `server.json`) are the published content on GitHub at `trunk-io/mcp-server`
2. **Working area** — registry submission tracking and progress files live in `.claude/registries/`, isolated from the public-facing content

The actual server code lives in `trunk-io/trunk2` at `ts/apps/mcp/` (app) and `ts/packages/mcp/` (package). This repo contains no server code.

## Important Context

- **Branding:** The MCP server product is called **Trunk Flaky Tests** (not "CI Autopilot" — that branding was retired). All copy should use "Trunk Flaky Tests".
- **Doc URLs:** Many external doc links still use `/ci-autopilot/` in the path (e.g. `docs.trunk.io/ci-autopilot/use-mcp-server/...`). These are trunk.io doc URLs that may need updating if/when the docs site restructures.

## Current Goal

Submit the Trunk MCP server to public registries. Each registry has its own tracking file under `.claude/registries/` with status checklists, submission steps, and blockers.

| Registry                | File                                           | Submission Method                    | Status                                         |
| ----------------------- | ---------------------------------------------- | ------------------------------------ | ---------------------------------------------- |
| Official MCP Registry   | `.claude/registries/official-mcp.md`           | CLI (`mcp-publisher`)                | Live (v1.1.0)                                  |
| Cursor MCP Registry     | `.claude/registries/cursor.md`                 | GitHub issue at `cursor/mcp-servers` | PR submitted (#318), awaiting review           |
| Claude Code Plugin      | `.claude/registries/claude-code-plugin.md`     | Web form                             | Repo created, needs testing + submission        |
| Cursor Marketplace      | `.claude/registries/cursor-marketplace.md`     | Web form                             | Repo created, needs submission                  |
| Smithery                | `.claude/registries/smithery.md`               | CLI (`smithery`)                     | Not started                                    |
| Glama                   | `.claude/registries/glama.md`                  | Web form / auto-index                | Not started                                    |
| awesome-mcp-servers     | `.claude/registries/awesome-mcp.md`            | Pull request                         | Not started                                    |

## Repo Structure

```
mcp-server/
├── README.md                  ← Public-facing docs (published to GitHub)
├── server.json                ← Official MCP registry manifest
├── CLAUDE.md                  ← Project instructions (this file)
├── .claude/
│   ├── settings.local.json
│   └── registries/            ← Per-registry submission tracking (working files)
│       ├── _template.md       ← Template for adding new registries
│       ├── official-mcp.md        ← Official MCP Registry (live, v1.1.0)
│       ├── cursor.md              ← Cursor MCP Registry (PR #318 pending)
│       ├── claude-code-plugin.md  ← Claude Code Plugin Directory
│       ├── cursor-marketplace.md  ← Cursor Marketplace Plugin
│       ├── smithery.md            ← Smithery registry
│       ├── glama.md               ← Glama registry
│       └── awesome-mcp.md         ← awesome-mcp-servers list
├── .trunk/                    ← Trunk CLI configuration
```

**Root files are public-facing.** Do not add working/draft files to the root. All tracking and progress goes in `.claude/`.

## Open Blockers (as of 2026-03-12)

### Shared

- **Team review** — description copy and tool list need sign-off
- **Public repo URL confirmation** — this repo (`trunk-io/mcp-server`) has no server code; server code is in trunk2. Likely fine (Linear's Cursor entry is similar).
- **Version number** — trunk2's `server.json` has `{{VERSION_HERE}}` placeholder; root `server.json` currently uses `0.1.0`

### Resolved

- ~~**Square SVG logo**~~ — available at https://trunk.io/branding/trunk.svg

### Official MCP Registry Only

- **Namespace decision** — `io.trunk/mcp-server` (DNS auth, cleaner branding) vs `io.github.trunk-io/mcp-server` (GitHub auth, easier). Recommendation: `io.trunk` via DNS.
- **DNS/HTTP verification** — if using `io.trunk`, need a TXT record or `/.well-known/mcp-registry-auth` on trunk.io

## What's Been Done

- Researched requirements for all 5 registries
- Created per-registry tracking files with status checklists and submission steps
- Drafted the Cursor submission (full GitHub issue template filled out in `.claude/registries/cursor.md`)
- Documented the official MCP registry process (`mcp-publisher` CLI workflow)
- Created `server.json` for the official MCP registry (at repo root)
- Created updated `README.md` with `mcp-name` comment, tool table, quick start configs for all 4 clients
- Rebranded all copy from "CI Autopilot" to "Trunk Flaky Tests"
- Consolidated all working files from `trunk-io/trunk2/.claude/skills/mcp-registry/` into this repo
- Organized repo so root is clean/public and working files are in `.claude/`

## The MCP Server

- **Endpoint:** `https://mcp.trunk.io/mcp`
- **Auth:** OAuth 2.0 + OpenID Connect
- **Transport:** streamable-http
- **Public tools:** `fix-flaky-test`, `setup-trunk-uploads`
- **Feature-flagged tools (not yet public):** `detect-frameworks`, `get-repo-id`, `get-clickhouse-db-schema`, `query-test-clickhouse-db`
- **Supported clients:** Cursor, Claude Code, GitHub Copilot, Gemini CLI
- **Docs:** https://docs.trunk.io/flaky-tests/use-mcp-server

## Reference Links

### Registries

- Official MCP Registry: https://registry.modelcontextprotocol.io
- Official registry repo: https://github.com/modelcontextprotocol/registry
- Official server.json schema: https://static.modelcontextprotocol.io/schemas/2025-12-11/server.schema.json
- Cursor registry repo: https://github.com/cursor/mcp-servers
- Cursor CONTRIBUTING.md: https://github.com/cursor/mcp-servers/blob/main/CONTRIBUTING.md
- Smithery: https://smithery.ai
- Glama: https://glama.ai/mcp/servers

### Trunk

- Server endpoint: https://mcp.trunk.io/mcp
- Docs: https://docs.trunk.io/flaky-tests/use-mcp-server
- Public repo: https://github.com/trunk-io/mcp-server
- Code (internal): `trunk-io/trunk2` at `ts/apps/mcp/` and `ts/packages/mcp/`
