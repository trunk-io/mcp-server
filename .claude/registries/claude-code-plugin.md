# Registry: Claude Code Plugin Directory

## Status: [ ] Not Started

- [x] Plugin repo created
- [ ] Plugin tested locally
- [ ] Submission form completed
- [ ] Listing verified live

## Details

| Field                     | Value                                                                                      |
| ------------------------- | ------------------------------------------------------------------------------------------ |
| **Registry URL**          | https://github.com/anthropics/claude-plugins-official                                      |
| **Listing URL**           | TBD — will be at `external_plugins/trunk/` once merged                                     |
| **Submission method**     | Web form at https://clau.de/plugin-directory-submission                                    |
| **Requires source code?** | No (hosted MCP server)                                                                     |
| **Plugin repo**           | https://github.com/trunk-io/claude-code-plugin                                             |
| **Local path**            | `~/TRUNK/claude-code-plugin`                                                               |
| **Date submitted**        |                                                                                            |
| **Date listed**           |                                                                                            |

## Plugin Structure

```
claude-code-plugin/
├── .claude-plugin/
│   └── plugin.json      # Plugin metadata
├── .mcp.json            # MCP server configuration
├── assets/
│   └── logo.svg         # Trunk logo
├── README.md
├── LICENSE
└── .gitignore
```

## Plugin Files

**`.claude-plugin/plugin.json`:**
```json
{
  "name": "trunk",
  "description": "Flaky test detection, root cause analysis, and fix suggestions for development teams.",
  "author": { "name": "Trunk", "url": "https://trunk.io" },
  "homepage": "https://trunk.io",
  "repository": "https://github.com/trunk-io/claude-code-plugin",
  "license": "MIT",
  "keywords": ["testing", "flaky-tests", "ci", "mcp"]
}
```

**`.mcp.json`:**
```json
{
  "mcpServers": {
    "trunk": {
      "type": "http",
      "url": "https://mcp.trunk.io/mcp"
    }
  }
}
```

## Steps

1. [x] Create plugin repo at `trunk-io/claude-code-plugin`
2. [ ] Test plugin locally with `/plugin install` in Claude Code
3. [ ] Submit via plugin directory submission form: https://clau.de/plugin-directory-submission
4. [ ] Wait for Anthropic review
5. [ ] Verify listing in `anthropics/claude-plugins-official` under `external_plugins/trunk/`

## Reference

- Claude Code plugin docs: https://code.claude.com/docs/en/plugins
- Plugin discovery docs: https://code.claude.com/docs/en/discover-plugins
- Official plugin directory: https://github.com/anthropics/claude-plugins-official
- Install command: `/plugin install trunk@claude-plugin-directory`
- Linear plugin (reference): https://github.com/anthropics/claude-plugins-official/tree/main/external_plugins/linear
- Stripe plugin (reference): https://github.com/anthropics/claude-plugins-official/tree/main/external_plugins/stripe

## Notes

- The plugin is minimal — just `plugin.json` + `.mcp.json` pointing to the hosted MCP server (same pattern as Linear and Stripe)
- OAuth handled by the MCP server itself; no auth config needed in the plugin
- Logo reused from cursor-plugin repo (`assets/logo.svg`)
