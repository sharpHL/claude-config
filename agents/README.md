# Agents Directory

Add your specialized agents here.

## Attribution

The agents in this directory are adapted from [claude-code-templates](https://github.com/davila7/claude-code-templates) by [@davila7](https://github.com/davila7), licensed under the MIT License. These templates provide expert agents for various domains and workflows.

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
