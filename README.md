# sharp-marketplace

Personal Claude Code plugins for development, trading, and research.

## Plugins

| Plugin | Description |
|--------|-------------|
| `common` | Code review, explain, summarize |
| `research` | Papers, reports, books, RSS |
| `trading` | Quantitative trading + A-stock |
| `dev` | Frontend, backend, testing |
| `devops` | Docker, CI/CD, deployment |

## Installation

### Use entire marketplace

```json
// .claude/settings.json
{
  "extraKnownMarketplaces": [
    "github:sharpHL/claude-config@main"
  ]
}
```

### Use specific plugin

```json
// .claude/settings.json
{
  "plugins": {
    "common": {
      "source": "github:sharpHL/claude-config@main:common"
    }
  }
}
```

### Local development

```json
{
  "plugins": {
    "common": {
      "source": "/Users/sharp/libs/myown/my-plugin/common"
    }
  }
}
```
