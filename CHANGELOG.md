# Changelog

All notable changes to the Claude Code Toolkit will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Planned
- Additional workflow automation hooks
- More algorithm engineering utilities
- Enhanced MCP server integrations
- Community contributions

## [2.0.0] - 2024-11-14

### Added - Workflow Commands
- **`/daily-market-brief`** - Market analysis brief generation (morning/midday/evening)
- **`/kb-sync`** - Obsidian knowledge base maintenance and health checks
- **`/intel-digest`** - Intelligence feed processing from FOLO and RSS sources
- **`/research-summary`** - AI/ML research paper analysis and summarization
- **`/algo-benchmark`** - Comprehensive algorithm performance benchmarking

### Added - New Agent Category: Productivity
- **`knowledge-curator`** - Obsidian vault management and PKM optimization
- **`intelligence-synthesizer`** - Multi-source intelligence gathering and synthesis

### Added - Data & AI Agents
- **`algorithm-engineer`** - Algorithm design, optimization, and complexity analysis
- **`etf-market-analyst`** - ETF and market analysis with technical indicators
- **`research-digest`** - Academic paper analysis and research tracking

### Enhanced
- Updated marketplace.json to version 2.0.0
- Added comprehensive workflow command documentation
- Created productivity agents directory with dedicated README
- Updated main README with new features and use cases
- Enhanced agents README with new categories and agents

### Structure
- New `/commands/workflow/` directory with 5 specialized commands
- New `/agents/productivity/` directory for knowledge and intelligence work
- Expanded `/agents/data-ai/` from 3 to 6 specialized agents

### Summary
- **Total Agents**: 17 → 22 (+5 new agents)
- **Total Commands**: 6 → 11 (+5 workflow commands)
- **New Categories**: Added Productivity agents
- **Focus Areas**: Algorithm engineering, knowledge management, market analysis, intelligence gathering

## [1.0.0] - 2025-10-25

### Added
- Initial release of Claude Code Toolkit Template
- Plugin structure and organization:
  - `.claude-plugin/plugin.json` manifest
  - Organized directories for commands, agents, skills
  - README guides in each directory
- Comprehensive documentation:
  - Best practices guide
  - Tips and tricks
  - CLAUDE.md project template
  - Contributing guidelines
- Repository essentials:
  - Detailed README with setup instructions
  - MIT License
  - .gitignore
  - CHANGELOG

### Documentation
- Comprehensive README with customization guide
- Best practices guide for Claude Code development
- Tips and tricks for productivity
- Component creation guides in each directory
- CLAUDE.md template for project configuration

[Unreleased]: https://github.com/sharpHL/claude-config/compare/v2.0.0...HEAD
[2.0.0]: https://github.com/sharpHL/claude-config/releases/tag/v2.0.0
[1.0.0]: https://github.com/sharpHL/claude-config/releases/tag/v1.0.0
