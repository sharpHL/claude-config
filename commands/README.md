# Custom Slash Commands

This directory contains custom slash commands for Claude Code.

## 🚀 Available Commands

### Included: Git Flow Commands (`git/`)

Complete Git Flow workflow automation commands:

**Core Workflow Commands:**
- `/git:feature <name>` - Create feature branches from develop
- `/git:release <version>` - Create release branches with versioning
- `/git:hotfix <name>` - Create emergency hotfix branches from main
- `/git:finish` - Complete and merge Git Flow branches
- `/git:flow-status` - Display comprehensive Git Flow status

**Utility Commands:**
- `/git:branch <description> [--type=feature|release|hotfix] [--project=name]` - Generate compliant branch names

**Usage Example:**
```bash
/git:branch "user authentication system" --type=feature --project=ecommerce
# Suggests: feature/ecommerce-user-authentication-system

/git:feature user-authentication
/git:finish
/git:flow-status
```

## 📋 Attribution

**Git Flow Commands**: These comprehensive Git Flow slash commands are adapted from [claude-code-templates](https://github.com/davila7/claude-code-templates) by [@davila7](https://github.com/davila7), licensed under the MIT License. They provide a robust Git Flow workflow implementation for Claude Code.

## ➕ Adding Your Own Commands

### Create Custom Commands
Add your own commands to extend the toolkit:

#### Command Structure
Create a new `.md` file in this directory:

```markdown
---
description: Your command description
tags: [tag1, tag2]
---

Your command prompt here...
```

### Example
Create a file `commands/review.md`:

```markdown
---
description: Review code changes for quality and best practices
tags: [review, code-quality]
---

Review the current code changes and provide feedback on:
- Code quality and best practices
- Potential bugs or issues
- Performance considerations
- Testing coverage
```

Then use it in Claude Code: `/review`

## Resources

- [Claude Code Documentation - Custom Commands](https://docs.claude.com/claude-code)
- [Git Flow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
