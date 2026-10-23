# Upstream

- Source: https://github.com/nextlevelbuilder/ui-ux-pro-max-skill
- Snapshot: commit `28327f2` (plugin version 2.15.0)
- Licence: MIT, see `LICENSE`
- Copied unmodified: the `.claude/skills/` directory only (7 skills). The folder layout is kept
  because the main skill runs its scripts from `${CLAUDE_PLUGIN_ROOT}/.claude/skills/...`.
- Not copied: the CLI, gallery, screenshots, previews, docs and translated READMEs.

## What runs code

Skills only; no hooks or MCP servers. Scripts run only when a skill is invoked and tells Claude to run them.

- `ui-ux-pro-max`: Python (3.8+) scripts that search and validate a local CSV database. No network access.
- `design` (logo and brand-image generation): calls image-generation services, only when
  `GEMINI_API_KEY`, `ATLASCLOUD_API_KEY` or `MUAPI_API_KEY` is set.
- `design-system`: a background-image helper and a token validator.
- `ui-styling`: `shadcn_add.py` runs the shadcn CLI through `npx`.
- `brand`: local Node scripts that extract colours and sync design tokens.
- `banner-design`, `slides`: instructions only.

To update, re-copy `.claude/skills/` from a reviewed upstream commit and change this file.
