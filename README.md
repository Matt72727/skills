# skills

Personal Claude Code skills, distributed as a plugin marketplace. This repo is the
single source of truth: install it once per device and every Claude Code surface on that
device (CLI, VS Code, desktop Code tab) uses the same skills.

## Install (once per device)

```
/plugin marketplace add Matt72727/skills
/plugin install my-skills@matt-skills
```

To also install everything-claude-code (pulled from github.com/worldflowai/everything-claude-code).
It bundles hooks and rules, so review them before enabling:

```
/plugin install everything-claude-code@matt-skills
```

The repo is public, so no GitHub login is needed to install.

### Or in one step: `~/.claude/settings.json`

```json
{
  "extraKnownMarketplaces": {
    "matt-skills": { "source": { "source": "git", "url": "https://github.com/Matt72727/skills.git" } }
  },
  "enabledPlugins": { "my-skills@matt-skills": true }
}
```

## What lives where

- `plugins/my-skills/skills/` - my skills (this repo).
- `.claude-plugin/marketplace.json` - lists my plugin plus third-party plugins to install.
- Skills synced from a claude.ai account (docx, pdf, ...) are not in this repo; they follow the account.
- Installed skills are loaded on demand (by matching description or `/skill-name`). Plugin hooks run automatically.

## Add a skill

Create `plugins/my-skills/skills/<skill-name>/SKILL.md`, bump `version` in
`plugins/my-skills/.claude-plugin/plugin.json`, and push.

## Update on another device

```
/plugin marketplace update matt-skills
```

## Bundled third-party skills

`brag` and `brag-slim` are copied from https://github.com/latent-spaces/brag
(MIT, by Shunit Haviv Hakimi; license in `plugins/my-skills/skills/brag/LICENSE`).
They are a snapshot of v0.4.0 and don't update automatically.
