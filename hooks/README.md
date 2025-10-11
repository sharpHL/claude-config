# Custom Hooks

This directory contains custom hooks for Claude Code automation.

## Usage

Hooks are shell scripts that execute in response to specific events in Claude Code.

## Example Hook Types

- **Pre-commit hooks** - Run before git commits
- **Post-command hooks** - Run after specific commands
- **File change hooks** - Trigger on file modifications

## Example

Create a file `hooks/pre-commit.sh`:

```bash
#!/bin/bash
# Run tests before commit
pytest tests/
```

Make it executable:
```bash
chmod +x hooks/pre-commit.sh
```

## Security Note

⚠️ Review all hook scripts before committing - ensure they don't contain:
- API keys or tokens
- Personal paths
- Sensitive credentials

## Resources

- [Claude Code Documentation - Hooks](https://docs.claude.com/claude-code)
