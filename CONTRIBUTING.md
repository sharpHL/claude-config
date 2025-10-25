# Contributing to Claude Code Toolkit

Thank you for your interest in contributing to the Claude Code Toolkit! This document provides guidelines and instructions for contributing.

## 🌟 How Can I Contribute?

### 1. Share Slash Commands
Have a useful slash command? We'd love to include it!

**What makes a good slash command:**
- Solves a common problem
- Clear, specific purpose
- Well-documented with examples
- Reusable across different projects

### 2. Create Agents
Specialized agents for specific tasks are always welcome.

**Agent requirements:**
- Clear, focused purpose
- Documented capabilities
- Systematic approach
- Examples of when to use

### 3. Improve Documentation
- Fix typos or unclear explanations
- Add more examples
- Create tutorials
- Improve existing guides

### 4. Report Issues
Found a bug or have a suggestion? Please open an issue!

### 5. Share Examples
Real-world usage examples help everyone learn.

## 📋 Contribution Process

### Step 1: Fork and Clone
```bash
# Fork the repository on GitHub
# Then clone your fork
git clone https://github.com/your-username/cc-toolkit.git
cd cc-toolkit
```

### Step 2: Create a Branch
```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/issue-description
```

### Step 3: Make Your Changes

#### Adding a Slash Command
1. Create a new `.md` file in `commands/`
2. Add frontmatter with description and tags
3. Write a clear, focused command prompt
4. Test it locally

Example:
```markdown
---
description: Brief description of what this command does
tags: [tag1, tag2, tag3]
parameters:
  - name: param1
    description: Parameter description
    required: false
---

Your command prompt here...
```

#### Adding an Agent
1. Create a new `.md` file in `agents/`
2. Define agent metadata in frontmatter
3. Document capabilities and approach
4. Specify tools the agent uses
5. Provide usage examples

Example:
```markdown
---
name: agent-name
description: What this agent does
tools: [Read, Write, Grep, Bash]
tags: [tag1, tag2]
---

Agent instructions here...
```

#### Improving Documentation
1. Edit the relevant `.md` file
2. Ensure formatting is consistent
3. Add examples where helpful
4. Check for broken links

### Step 4: Test Your Changes

#### Local Testing
```bash
# Create a test marketplace configuration
# In your Claude Code settings:
{
  "pluginMarketplaces": [
    {
      "name": "local-test",
      "url": "file:///path/to/cc-toolkit/parent"
    }
  ]
}

# Install the plugin
/plugin install cc-toolkit@local-test

# Test your changes
# Try the new command or agent
# Verify it works as expected
```

#### Quality Checks
- [ ] Command/agent works as intended
- [ ] Documentation is clear and complete
- [ ] No typos or grammar issues
- [ ] Examples are accurate
- [ ] Tags are relevant

### Step 5: Commit Your Changes

Use clear, descriptive commit messages following conventional commits:

```bash
git add .
git commit -m "Add: new performance profiling command"
# or
git commit -m "Fix: typo in security-audit command"
# or
git commit -m "Docs: improve usage examples"
```

**Commit message format:**
```
<type>: <description>

[optional body]

[optional footer]
```

**Types:**
- `Add:` - New feature or component
- `Fix:` - Bug fix
- `Docs:` - Documentation changes
- `Style:` - Formatting changes
- `Refactor:` - Code refactoring
- `Test:` - Adding or updating tests
- `Chore:` - Maintenance tasks

### Step 6: Push and Create Pull Request

```bash
git push origin feature/your-feature-name
```

Then create a pull request on GitHub with:
- Clear title describing the change
- Description of what changed and why
- Any relevant issue numbers (Fixes #123)
- Screenshots if applicable

## ✅ Pull Request Guidelines

### Before Submitting
- [ ] Changes work locally
- [ ] Documentation is updated
- [ ] Commit messages are clear
- [ ] No unnecessary files included
- [ ] Follows existing style/format

### PR Description Should Include
1. **What**: What changes were made
2. **Why**: Why these changes were needed
3. **How**: How to test the changes
4. **Screenshots**: If applicable

### Example PR Description
```markdown
## Add Performance Profiling Command

### What
Adds a new `/profile-performance` command that analyzes application performance and provides optimization recommendations.

### Why
Many developers need to profile their applications but don't have a systematic approach. This command provides a structured workflow.

### How to Test
1. Install the plugin locally
2. Run `/profile-performance` in a test project
3. Verify it analyzes performance metrics
4. Check that recommendations are actionable

### Changes
- New command: `commands/profile-performance.md`
- Updated README with command documentation
- Added usage example to `examples/usage-examples.md`

Fixes #42
```

## 🎨 Style Guidelines

### Markdown Files
- Use ATX-style headers (`#` not underlines)
- Use fenced code blocks with language specifiers
- Include examples for commands and agents
- Keep lines under 100 characters when possible

### Commands
- Clear, imperative descriptions
- Specific, actionable prompts
- Include examples
- Add relevant tags for discoverability

### Agents
- Define clear scope and purpose
- Document systematic approach
- Specify required tools
- Provide usage examples

### Documentation
- Write clearly and concisely
- Use examples liberally
- Structure with clear headings
- Include code snippets where helpful

## 🐛 Reporting Issues

### Bug Reports
Include:
- Clear description of the issue
- Steps to reproduce
- Expected vs actual behavior
- Environment details (Claude Code version, OS)
- Screenshots if applicable

### Feature Requests
Include:
- Clear description of the feature
- Why it would be useful
- Example use cases
- Any implementation ideas

## 💡 Suggestions

### Good Ideas for Contributions
- Commands for common workflows (testing, deployment, etc.)
- Language-specific agents (Python expert, Rust expert, etc.)
- Framework-specific commands (React, Django, etc.)
- Integration examples with popular tools
- Video tutorials or blog posts
- Translations (if applicable)

### Before Starting Large Features
For significant changes:
1. Open an issue first to discuss
2. Get feedback on the approach
3. Ensure it aligns with project goals
4. Coordinate with maintainers

## 📞 Getting Help

- **Questions**: Open a GitHub Discussion
- **Issues**: Open a GitHub Issue
- **Real-time**: Join our community chat (if available)
- **Email**: [maintainer email]

## 🙏 Code of Conduct

Be respectful and constructive:
- Be kind and courteous
- Respect different viewpoints
- Accept constructive criticism
- Focus on what's best for the community
- Show empathy toward others

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

## 🎉 Recognition

Contributors will be recognized in:
- README acknowledgments
- CHANGELOG for significant contributions
- GitHub contributors page

Thank you for making Claude Code Toolkit better!
