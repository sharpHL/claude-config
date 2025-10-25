# Skills Directory

Add your Claude Code skills here.

## What are Skills?

Skills are model-invoked tools that Claude can use autonomously when appropriate. Unlike commands (user-invoked) or agents (explicitly called), skills are available for Claude to use automatically when they're relevant to the task.

## How to Create a Skill

1. Create a new `.md` file in this directory
2. Add frontmatter with skill metadata
3. Define the skill's functionality

## Example Structure

```markdown
---
name: skill-name
description: What this skill does
invocation: When Claude should use this skill
---

Skill implementation details...
```

## When to Use Skills

Create skills for:
- Common operations you want Claude to perform automatically
- Domain-specific knowledge or procedures
- Specialized formatting or processing tasks
- Integration with external tools or workflows

## Resources

- [Skills Documentation](https://docs.claude.com/en/docs/claude-code/skills.md)
