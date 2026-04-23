# bolster-marketplace

A [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) containing two plugins:

| Plugin | Repo | Purpose |
|--------|------|---------|
| [`bolster`](https://github.com/andrewbolster/claude-plugin) | `andrewbolster/claude-plugin` | Personal best practices — Python/uv standards, dev environment, voice/style, tooling patterns |
| [`data-science`](https://github.com/bd-vitalstatistix/claude-plugin) | `bd-vitalstatistix/claude-plugin` | Black Duck Data Science team — LLM Gateway, Atlassian/JIRA, data analytics, content creation |

## Installation

```bash
# Install the full marketplace
claude plugin marketplace add git@github.com:bd-vitalstatistix/claude-marketplace.git

# Or install individual plugins directly from their own repos
claude plugin add git@github.com:andrewbolster/claude-plugin.git
claude plugin add git@github.com:bd-vitalstatistix/claude-plugin.git
```

## Plugins

### `bolster`

Personal, non-work-specific capabilities. Safe to use in any context.

Repo: [andrewbolster/claude-plugin](https://github.com/andrewbolster/claude-plugin)

Skills: `uv-run`, `markitdown`, `lsof-patterns`, `git-attribution`, `dev-environment`, `voice-style`, `data-verification`

### `data-science`

Work-specific capabilities for the Black Duck Data Science team. Contains internal tooling references and org-specific context.

Repo: [bd-vitalstatistix/claude-plugin](https://github.com/bd-vitalstatistix/claude-plugin)

Skills: `professional-context`, `gateway-management`, `atlassian-workflows`, `data-analytics`, `content-creation`, `project-management`

## Structure

This repo is the marketplace index. Each plugin lives in its own standalone repo:

```
marketplace.json          ← references external repos
README.md
plugins/                  ← local copies (kept in sync with sub-repos)
├── bolster/              → github.com/andrewbolster/claude-plugin
└── data-science/         → github.com/bd-vitalstatistix/claude-plugin
```
