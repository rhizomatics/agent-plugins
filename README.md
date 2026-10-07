# Rhizomatics Agent Plugins

Plugin marketplace for [Rhizomatics](https://github.com/rhizomatics) open source tools. Each plugin
carries skills that teach a coding agent how to use one of the tools.

## Install

In [Claude Code](https://claude.com/claude-code), add the marketplace once:

```bash
claude plugin marketplace add rhizomatics/agent-plugins
```

Then install the plugins you want:

```bash
claude plugin install homeassistant-repl@rhizomatics
```

## Plugins

| Plugin | What it teaches an agent | Source |
| ------ | ------------------------ | ------ |
| `homeassistant-repl` | Running Python against a running Home Assistant with `ha-repl`, for custom component development | [rhizomatics/homeassistant-repl](https://github.com/rhizomatics/homeassistant-repl) |

## Adding a plugin

The plugin lives in the tool's own repo, so its skills are versioned with the code they describe:

1. In the tool's repo, add `.claude-plugin/plugin.json` and a `skills/<name>/SKILL.md`.
2. Add an entry for it to [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) here,
   with a `github` source pointing at that repo.
3. Run `claude plugin validate .` in both repos.
