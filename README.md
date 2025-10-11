# Claude Code Configuration

Personal configuration and preferences for [Claude Code](https://claude.com/claude-code).

## Features

- **User-level preferences** - English-only responses, Python tooling with `uv`
- **Code style standards** - Type hints, 100-char limit, explicit naming
- **Git workflow** - Conventional commits, testing requirements
- **Custom commands** - Reusable slash commands (coming soon)

## Quick Start

### Option 1: Symbolic Links (Recommended)

```bash
# Clone the repository
git clone https://github.com/yourusername/claude-config.git
cd claude-config

# Backup existing configuration
mv ~/.claude/CLAUDE.md ~/.claude/CLAUDE.md.backup

# Create symbolic link
ln -sf $(pwd)/CLAUDE.md ~/.claude/CLAUDE.md

# Restart Claude Code
```

### Option 2: Direct Copy

```bash
# Clone the repository
git clone https://github.com/yourusername/claude-config.git

# Copy configuration files
cp claude-config/CLAUDE.md ~/.claude/

# Restart Claude Code
```

### Option 3: Make ~/.claude a Git Repo

```bash
# Navigate to Claude directory
cd ~/.claude

# Initialize git (if not already a repo)
git init

# Add remote
git remote add origin https://github.com/yourusername/claude-config.git

# Pull configuration
git pull origin main

# Only track safe files (see .gitignore)
git add CLAUDE.md settings.json
git commit -m "feat: sync configuration"
```

## Repository Structure

```
claude-config/
├── README.md           # This file
├── .gitignore         # Security rules - prevents committing sensitive data
├── CLAUDE.md          # User-level preferences and coding standards
├── commands/          # Custom slash commands (optional)
└── hooks/             # Custom hooks (optional)
```

## Configuration Files

### CLAUDE.md
User-level preferences that apply to all Claude Code sessions:
- Language requirements (English-only)
- Python tooling preferences (`uv` over `pip`)
- Code style standards
- Git workflow conventions
- Testing and documentation requirements
- Response style preferences

### settings.json (Optional)
Claude Code editor and tool settings. Review for personal paths before committing.

## Syncing Changes

### From This Repo to Your Machine

```bash
cd ~/claude-config  # or wherever you cloned it
git pull
cp CLAUDE.md ~/.claude/  # if not using symlinks
```

### From Your Machine to This Repo

```bash
cd ~/claude-config
cp ~/.claude/CLAUDE.md .
git add CLAUDE.md
git commit -m "chore: update preferences"
git push
```

## Security Notes

⚠️ **NEVER commit these files** (already in `.gitignore`):
- `history.jsonl` - Your chat history
- `debug/` - Debug logs
- `projects/` - Project-specific data
- `todos/` - Task lists
- `shell-snapshots/` - Shell command history

✅ **Safe to commit**:
- `CLAUDE.md` - Your preferences
- `settings.json` - After reviewing for personal paths
- Custom commands and hooks (if no secrets)

## Customization

Feel free to fork and modify for your needs:

1. Edit `CLAUDE.md` to match your preferences
2. Add custom slash commands in `commands/`
3. Create hooks in `hooks/` for automation
4. Share your setup with others!

## Version History

- **v1.0.0** - Initial configuration with core preferences

## Resources

- [Claude Code Documentation](https://docs.claude.com/claude-code)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [uv - Python Package Manager](https://github.com/astral-sh/uv)

## License

MIT License - Feel free to use and adapt!

---

**Note**: This is a personal configuration repository. Adapt it to your workflow and preferences!
