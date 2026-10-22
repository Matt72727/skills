# Upstream

- Source: https://github.com/thedotmack/claude-mem
- Snapshot: commit `bbb3379` (plugin version 15.0.1)
- Licence: Apache-2.0, see `LICENSE` and `NOTICE`
- Copied unmodified: `plugin/skills/` only (27 skills).
- Not copied: the memory worker, database, hooks, and MCP server.

## Limitation

18 of these skills (for example `mem-search`) call the claude-mem search tools
(`mcp__plugin_claude-mem_mcp-search__*`). Those tools exist only when the upstream
claude-mem plugin is installed, which also runs background hooks that record sessions.
Without it, those skills have nothing to query. The rest work on their own.
