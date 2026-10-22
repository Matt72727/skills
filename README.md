# skills

Personal Claude Code skills, distributed as a plugin marketplace. This repo is the
single source of truth: install it once per device and every Claude Code surface on that
device (CLI, VS Code, desktop Code tab) uses the same skills.

## Install (once per device)

```
/plugin marketplace add Matt72727/skills
/plugin install my-skills@matt-skills
```

That installs my skills (brag, brag-slim, hello-skill). Nothing is fetched from other repos.

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

## Optional vendored plugins (skills only)

Installed separately, so they cost nothing on a device that doesn't install them. Each is a
snapshot (source commit in its `UPSTREAM.md`) and does not auto-update. Hooks, MCP servers,
agents and commands are not included.

```
/plugin install ecc@matt-skills
/plugin install claude-mem-skills@matt-skills
```

- `ecc`: 311 skills from https://github.com/affaan-m/ecc (MIT). Every installed skill adds its
  description to every session, so install it only where you want it.
- `claude-mem-skills`: 27 skills from https://github.com/thedotmack/claude-mem (Apache-2.0).
  18 of them (such as `mem-search`) need the upstream claude-mem plugin's memory server, which
  is not included and records sessions through background hooks. See its `UPSTREAM.md`.

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
