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

### 🚀 **Currently Available**
- **6 Git Flow Commands** - Complete branching workflow automation
- **17 Specialized Agents** - Data & AI, Podcast Creation, Programming experts
- **Project Template** - Comprehensive CLAUDE.md with development best practices
- **Documentation** - Best practices, tips, and examples

### 🚧 **Framework Ready**
- **Skills** - Framework for modular capabilities
- **Hooks** - Framework for automation workflows
- **Templates** - Ready for language-specific configurations
- **Extensions** - Add your own commands and agents

### 🔧 **Integrated MCP Servers**
Model Context Protocol servers for enhanced capabilities:
- **Context7** - Enhanced context management and retrieval
- **Chrome DevTools** - Browser automation and debugging
- **Sequential Thinking** - Structured reasoning and analysis

*Automatically configured via npm packages - no manual setup required*

### Slash Commands (`/commands`)
Custom commands for streamlined workflows:

**Git Flow Commands** (`/commands/git/`):
- Complete branching workflow automation
- See `/commands/README.md` for detailed usage and attribution

**Custom Commands**:
- Add your own commands to extend functionality
- See `/commands/README.md` for creation guide

### Agents (`/agents`)
Specialized sub-agents for focused tasks:

**Included Agents**:
- **17 Expert Agents** across 3 categories
- **Data & AI**: Quant analysis, AI engineering, data science
- **Podcast Creation**: Research, production, marketing team
- **Programming**: Python, TypeScript, Shell scripting experts

**Custom Agents**:
- Create your own specialized agents
- Extend with domain-specific expertise
- See `/agents/README.md` for complete list and creation guide

*See `/agents/README.md` for complete list and attribution*

### Skills (`/skills`)
Modular capabilities (framework for future extensions):
- Framework-specific helpers
- Language tooling integration
- Development workflow utilities
- *(Coming soon: Create reusable skills!)*

### Hooks (`/hooks`)
Automated workflows (framework for future extensions):
- Pre-commit checks
- Test automation
- Build and deployment helpers
- *(Coming soon: Automate repetitive tasks!)*

### Templates (`/templates`)
Project configuration templates:
- `CLAUDE.md` - Comprehensive project template with Python, Git Flow, and development best practices
- Language-specific configurations *(coming soon)*
- Framework boilerplates *(coming soon)*

### Documentation (`/docs`)
- **Best Practices** - Development workflow guidelines and tips
- **Tips & Tricks** - Productivity hacks and shortcuts
- **Examples** - Usage examples and demonstrations
- *(Coming soon: In-depth guides)*

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
# For local installation
cp templates/CLAUDE.md ./.claude/

# For plugin installation
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
│   └── marketplace.json    # Plugin manifest
├── mcp-servers/            # 🔧 MCP server configurations
│   ├── .mcp.json         # MCP server setup
│   └── README.md          # MCP installation guide
├── commands/                # ✅ Slash commands (Git Flow)
├── agents/                  # ✅ Specialized agents (18 total)
│   ├── data-ai/            # Data & AI specialists
│   ├── podcast-creator-team/ # Podcast production team
│   └── programming-languages/ # Language experts
├── skills/                  # 🚧 Modular skills (framework)
├── hooks/                   # 🚧 Automation hooks (framework)
├── templates/               # ✅ Configuration templates
│   └── CLAUDE.md           # Project template
├── examples/                # 📋 Usage examples (README)
├── docs/                    # ✅ Documentation
│   ├── best-practices.md
│   └── tips-and-tricks.md
├── README.md               # This file
├── CLAUDE.md               # Project configuration
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

This toolkit builds upon excellent open-source foundations. See individual directories for specific attributions to contributors and source projects.

---

**Questions or Issues?** Open an issue on [GitHub](https://github.com/sharpHL/claude-config/issues)
