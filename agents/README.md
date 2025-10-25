# Agents Directory

Specialized agents for focused tasks and domain-specific expertise.

## 🚀 Available Agents

### Included Agents

#### 📊 Data & AI Agents (`data-ai/`)

- **`quant-analyst`** - Quantitative finance and algorithmic trading specialist
  - Trading strategy development and backtesting
  - Risk metrics and portfolio optimization
  - Time series analysis and forecasting

- **`ai-engineer`** - AI/ML implementation and deployment expert
  - Model deployment and MLOps workflows
  - Infrastructure scaling and optimization
  - Production AI system architecture

- **`data-scientist`** - Data analysis and modeling specialist
  - Statistical analysis and data visualization
  - Machine learning model development
  - Data pipeline creation and validation

### 🎙️ Podcast Creation Team (`podcast-creator-team/`)

**Core Production Team:**
- **`comprehensive-researcher`** - Deep research and content analysis
- **`episode-orchestrator`** - Podcast episode planning and coordination
- **`project-supervisor-orchestrator`** - Overall project management

**Content & Marketing:**
- **`social-media-copywriter`** - Social media content creation
- **`market-research-analyst`** - Market trends and audience analysis
- **`podcast-trend-scout`** - Emerging trends identification
- **`seo-podcast-optimizer`** - SEO optimization for podcast content

**Specialized Experts:**
- **`academic-research-synthesizer`** - Academic research integration
- **`guest-outreach-coordinator`** - Guest booking and coordination
- **`twitter-ai-influencer-manager`** - Social media influencer strategy
- **`podcast-editor`** - Content editing and quality control

### 💻 Programming Language Experts (`programming-languages/`)

- **`python-pro`** - Python development expert
  - Advanced Python patterns and best practices
  - Package management and virtual environments
  - Performance optimization and debugging

- **`typescript-pro`** - TypeScript and JavaScript specialist
  - Type-safe development patterns
  - Modern JavaScript/TypeScript features
  - Framework integration and architecture

- **`shell-scripting-pro`** - Bash and shell scripting expert
  - Advanced shell scripting techniques
  - System administration automation
  - DevOps pipeline scripting

### ➕ Create Your Own Agents

Add custom agents to extend the toolkit with your own specialized expertise:

## 📋 Attribution

**Included agents** are adapted from [claude-code-templates](https://github.com/davila7/claude-code-templates) by [@davila7](https://github.com/davila7), licensed under the MIT License. These templates provide expert agents for various domains and workflows with proven patterns for specialized task execution.

**Custom agents** can be added following the same structure and patterns.

## How to Create an Agent

1. Create a new `.md` file in this directory
2. Add frontmatter with agent metadata
3. Define the agent's behavior and capabilities

## Example Structure

```markdown
---
name: agent-name
description: What this agent specializes in
tools: [Read, Write, Edit, Bash, Grep, Glob]
tags: [tag1, tag2]
---

You are a [specialized role] focused on [specific task].

## Core Responsibilities
- Responsibility 1
- Responsibility 2

## Approach
Describe the systematic approach this agent should take

## Best Practices
Guidelines the agent should follow

## Output Format
How the agent should present results
```

## Agent Best Practices

- **Focused Expertise**: Each agent should specialize in a specific domain
- **Clear Scope**: Define what the agent does and doesn't handle
- **Systematic Approach**: Document the methodology the agent uses
- **Tool Usage**: Specify which tools the agent needs
- **Examples**: Include when to use this agent

## Resources

- [Sub-agents Documentation](https://docs.claude.com/en/docs/claude-code/sub-agents.md)
- [Best Practices](../docs/best-practices.md)
