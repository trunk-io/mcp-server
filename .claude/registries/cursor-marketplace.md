# Registry: Cursor Marketplace Plugin

## Status: [ ] Not Started

- [x] Plugin repo created
- [ ] Submission completed
- [ ] Listing verified live

## Details

| Field                     | Value                                                    |
| ------------------------- | -------------------------------------------------------- |
| **Marketplace URL**       | https://cursor.com/marketplace                           |
| **Listing URL**           | TBD                                                      |
| **Submission method**     | Web form at https://cursor.com/marketplace/publish       |
| **Alternative contact**   | kniparko@anysphere.com                                   |
| **Plugin repo**           | https://github.com/trunk-io/cursor-plugin                |
| **Local path**            | (not currently cloned locally)                           |
| **Date submitted**        |                                                          |
| **Date listed**           |                                                          |

## Context

This is separate from the Cursor MCP Registry submission (tracked in `cursor.md`). The registry submission (issue #317 / PR #318) adds Trunk to Cursor's built-in MCP server list. The **marketplace plugin** is a separate listing on cursor.com/marketplace that users can browse and install.

## Plugin Structure

```
cursor-plugin/
├── .cursor-plugin/
│   └── plugin.json      # Plugin metadata
├── mcp.json             # MCP server configuration
├── assets/
│   └── logo.svg         # Trunk logo
├── README.md
└── .gitignore
```

## Steps

1. [x] Create plugin repo at `trunk-io/cursor-plugin`
2. [ ] Submit at https://cursor.com/marketplace/publish (or email kniparko@anysphere.com)
3. [ ] Wait for Cursor team review
4. [ ] Verify listing on cursor.com/marketplace

## Reference

- Cursor plugin repo: https://github.com/trunk-io/cursor-plugin
- Cursor marketplace: https://cursor.com/marketplace
- Related: Cursor MCP Registry submission tracked in `cursor.md` (issue #317, PR #318)

## Notes

- The plugin repo is already public at `trunk-io/cursor-plugin`
- This marketplace submission is independent of the MCP registry PR (#318) — both should be done
- Marketplace gives better discoverability for users browsing cursor.com
