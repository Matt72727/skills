# skills

Personal Claude Code skills, distributed as a plugin marketplace.

## Install (once per machine)

```
/plugin marketplace add Matt72727/skills
/plugin install my-skills@matt-skills
```

The repo is private, so the machine needs GitHub access (`gh auth login` or an SSH key).

## Add a skill

Create `plugins/my-skills/skills/<skill-name>/SKILL.md`, bump `version` in
`plugins/my-skills/.claude-plugin/plugin.json`, and push.

## Update on another machine

```
/plugin marketplace update matt-skills
```
