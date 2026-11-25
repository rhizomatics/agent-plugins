# Rhizomatics Agent Plugins

[![managed by hq](https://raw.githubusercontent.com/rhizomatics/hq/main/assets/badge-managed-by-hq.svg)](https://hq.rhizomatics.org.uk/)

Plugin marketplace for [Rhizomatics](https://www.rhizomatics.org.uk) open source tools. Each plugin carries skills that teach a coding agent how to use one of the tools.

## Install

In [Claude Code](https://claude.com/claude-code), add the marketplace once:

```bash
claude plugin marketplace add rhizomatics/agent-plugins
```

Then install the plugins you want:

```bash
claude plugin install homeassistant-repl@rhizomatics
```

For other agents (GitHub Copilot, Codex, Cursor, Gemini and more), the [`skills` CLI](https://skills.sh) installs a
plugin's skills straight from its folder, e.g.

```bash
npx skills add https://github.com/rhizomatics/homeassistant-repl/tree/main/plugin/skills/ha-repl
```

## Plugins

| Plugin | What it teaches an agent | Source |
| ------ | ------------------------ | ------ |
| `homeassistant-repl` | Running Python against a running Home Assistant with `ha-repl`, for custom component development | [rhizomatics/homeassistant-repl](https://github.com/rhizomatics/homeassistant-repl) |

## Adding a plugin

The plugin lives in the tool's own repo, so its skills are versioned with the code they describe, in a folder of
its own (`plugin/`), so that folder can be submitted to the Claude plugin directory without the tool's code:

1. In the tool's repo, add `plugin/.claude-plugin/plugin.json`, a square `plugin/.claude-plugin/icon.png` and
   `plugin/skills/<name>/SKILL.md`. Keep the folder to Markdown, JSON and images.
2. Add an entry for it to [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) here, with a
   `git-subdir` source: `url` the tool's repo, `path` `plugin`.
3. Run `claude plugin validate .` here and `claude plugin validate plugin` in the tool's repo.
