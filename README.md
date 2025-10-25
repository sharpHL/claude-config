# Claude Code Toolkit

A curated collection of [Claude Code](https://claude.com/claude-code) commands, agents, skills, and best practices to supercharge your development workflow.

## ✨ Features

- **Slash Commands** - Reusable prompts for common development tasks
- **Specialized Agents** - Expert agents for specific domains and workflows
- **Skills** - Modular capabilities that can be invoked on-demand
- **Hooks** - Automation for repetitive tasks and workflows
- **Templates** - Project configuration templates (CLAUDE.md)
- **Best Practices** - Curated guides and tips for Claude Code mastery
- **Examples** - Real-world usage demonstrations

## 🚀 Quick Start

### Installation

Install the plugin using Claude Code's plugin system:

```bash
# Add the plugin marketplace (if using GitHub)
# In Claude Code settings or via command
/plugin add-marketplace https://github.com/sharpHL/claude-config

# Install the toolkit
/plugin install claude-config
```

### Local Development/Testing

For local testing or customization:

```bash
# Clone the repository
git clone https://github.com/sharpHL/claude-config.git
cd claude-config

# Add as local marketplace in Claude Code settings.json
{
  "pluginMarketplaces": [
    {
      "name": "local",
      "url": "file:///path/to/claude-config/parent"
    }
  ]
}

# Install from local marketplace
/plugin install claude-config@local
```

## 📦 What's Included

### Slash Commands (`/commands`)
Custom commands for streamlined workflows:

**Git Flow Commands** (`/commands/git/`):
- `/feature <name>` - Create feature branches from develop
- `/release <version>` - Create release branches with versioning
- `/hotfix <name>` - Create emergency hotfix branches from main
- `/finish` - Complete and merge Git Flow branches
- `/flow-status` - Display comprehensive Git Flow status

*Source: [claude-code-templates](https://github.com/davila7/claude-code-templates) by @davila7 (MIT License)*

*(Add your own commands!)*

### Agents (`/agents`)
Specialized sub-agents for focused tasks:
- Code review and analysis agents
- Security audit specialists
- Performance optimization experts
- *(Extend with domain-specific agents!)*

### Skills (`/skills`)
Modular capabilities:
- Framework-specific helpers
- Language tooling integration
- Development workflow utilities
- *(Create reusable skills!)*

### Hooks (`/hooks`)
Automated workflows:
- Pre-commit checks
- Test automation
- Build and deployment helpers
- *(Automate repetitive tasks!)*

### Templates (`/templates`)
Project configuration templates:
- `CLAUDE.md` - Project-level preferences and standards
- Language-specific configurations
- Framework boilerplates

### Documentation (`/docs`)
- **Best Practices** - How to get the most from Claude Code
- **Tips & Tricks** - Productivity hacks and shortcuts
- **Guides** - Deep dives into specific topics

## 🎯 Usage Examples

### Using Slash Commands
```bash
# List available commands
/help

# Use a custom command from this toolkit
/your-custom-command [parameters]
```

### Invoking Agents
Claude Code will automatically suggest relevant agents, or you can explicitly request them:
```
"Use the security-audit agent to review this authentication code"
```

### Applying Templates
Copy templates to your project:
```bash
cp ~/.claude/plugins/claude-config/templates/CLAUDE.md ./.claude/
```

## 🛠️ Customization

### Adding Your Own Commands

1. Create a new file in `commands/`:
```markdown
---
description: Your command description
tags: [tag1, tag2]
---

Your command prompt here...
```

2. Test locally before publishing

### Creating Custom Agents

1. Add to `agents/` directory:
```markdown
---
name: my-agent
description: What your agent does
tools: [Read, Write, Grep]
tags: [domain, specialty]
---

Agent instructions and behavior...
```

2. Document capabilities and usage

## 📂 Repository Structure

```
claude-config/
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest
├── commands/                # Slash commands
├── agents/                  # Specialized agents
├── skills/                  # Modular skills
├── hooks/                   # Automation hooks
├── templates/               # Configuration templates
│   └── CLAUDE.md           # Project template
├── examples/                # Usage examples
├── docs/                    # Documentation
│   ├── best-practices.md
│   └── tips-and-tricks.md
├── README.md               # This file
├── CLAUDE.md               # This plugin's config
├── CONTRIBUTING.md         # Contribution guide
├── CHANGELOG.md           # Version history
└── LICENSE                # MIT License
```

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- How to submit commands and agents
- Code style guidelines
- Testing procedures
- Pull request process

**Quick contribution checklist:**
- [ ] Test your changes locally
- [ ] Follow existing format and style
- [ ] Update documentation
- [ ] Add examples if applicable

## 📖 Resources

- [Claude Code Documentation](https://docs.claude.com/claude-code)
- [Plugin Development Guide](https://docs.claude.com/en/docs/claude-code/plugins)
- [Sub-agents Documentation](https://docs.claude.com/en/docs/claude-code/sub-agents)
- [Slash Commands Guide](https://docs.claude.com/en/docs/claude-code/slash-commands)

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

## 🙏 Acknowledgments

Built with ❤️ for the Claude Code community.

### Special Thanks

- **Git Flow Commands**: The comprehensive Git Flow slash commands (`/feature`, `/release`, `/hotfix`, `/finish`, `/flow-status`) are adapted from [claude-code-templates](https://github.com/davila7/claude-code-templates) by [@davila7](https://github.com/davila7), licensed under the MIT License. These commands provide a robust Git Flow workflow implementation for Claude Code.

---

**Questions or Issues?** Open an issue on [GitHub](https://github.com/sharpHL/claude-config/issues)
