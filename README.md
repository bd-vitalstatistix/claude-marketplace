# bolster-marketplace

A [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) containing two plugins:

| Plugin | Purpose |
|--------|---------|
| [`bolster`](./plugins/bolster/) | Personal best practices — Python/uv standards, dev environment, voice/style, tooling patterns |
| [`data-science`](./plugins/data-science/) | Black Duck Data Science team — LLM Gateway, Atlassian/JIRA, data analytics, content creation |

## Installation

```bash
# Install the full marketplace
claude plugin marketplace add git@github.com:bd-vitalstatistix/claude-marketplace.git

# Or install individual plugins directly
claude plugin add git@github.com:bd-vitalstatistix/claude-marketplace.git#plugins/bolster
claude plugin add git@github.com:bd-vitalstatistix/claude-marketplace.git#plugins/data-science
```

## Plugins

### `bolster`

Personal, non-work-specific capabilities. Safe to use in any context.

Skills: `uv-run`, `markitdown`, `lsof-patterns`, `git-attribution`, `dev-environment`, `voice-style`, `data-verification`

### `data-science`

Work-specific capabilities for the Black Duck Data Science team. Contains internal tooling references and org-specific context.

Skills: `professional-context`, `gateway-management`, `atlassian-workflows`, `data-analytics`, `content-creation`, `project-management`

## Structure

```
marketplace.json
plugins/
├── bolster/
│   ├── .claude-plugin/plugin.json
│   └── skills/
│       ├── uv-run/
│       ├── markitdown/
│       ├── lsof-patterns/
│       ├── git-attribution/
│       ├── dev-environment/
│       ├── voice-style/
│       └── data-verification/
└── data-science/
    ├── .claude-plugin/plugin.json
    └── skills/
        ├── professional-context/
        ├── gateway-management/
        ├── atlassian-workflows/
        ├── data-analytics/
        ├── content-creation/
        └── project-management/
```

## Future

The intention is to split each plugin into its own git sub-repo, allowing the personal (`bolster`) and work (`data-science`) plugins to be versioned and distributed independently.
