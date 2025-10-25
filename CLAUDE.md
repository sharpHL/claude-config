# User-Level Memory and Preferences

## 🌍 Language and Communication
**CRITICAL REQUIREMENT**: All responses, thoughts, code comments, and outputs MUST be in English, regardless of input language (including Chinese queries).

This applies to:
- Response messages and explanations
- Thinking/reasoning processes
- Code comments and documentation
- Output results and error messages
- Git commit messages

## 📝 Toolkit Development
**Note**: This is a Claude Code plugin toolkit containing Markdown-based commands and agents. No traditional programming language tooling is required for contributing.

**When contributing agents or commands:**
- Follow existing Markdown formatting
- Include proper frontmatter metadata
- Test locally before submitting
- Update marketplace.json with new entries

## 📁 Project Organization
- Prefer flat directory structures over deeply nested hierarchies
- Use clear, descriptive folder names: `src/`, `tests/`, `docs/`, `scripts/`
- Keep configuration files at project root
- Maintain consistent naming conventions across projects

## 💻 Code Style
- **Naming**: Use meaningful, descriptive variable and function names
- **Clarity**: Prefer explicit over implicit (readability over cleverness)
- **Length**: Maximum line length of 100 characters
- **Types**: Always use type hints in Python code
- **Standards**: Follow language-specific best practices
- **Content Generation**: Generate minimal, accurate content; all generated content is technical debt

## 🔄 Git Workflow

**Note**: This section documents the Git Flow commands provided by this toolkit for use in other projects. This toolkit repository itself uses a simplified workflow with `main` branch.

**For projects using the Git Flow commands:**

**Core Commands:**
- `/git:feature <name>` - Create feature branch from develop
- `/git:release <version>` - Create release branch from develop
- `/git:hotfix <name>` - Create hotfix branch from main
- `/git:finish` - Complete and merge current branch
- `/git:flow-status` - Check repository status
- `/git:branch <description>` - Generate Git Flow compliant branch names

**Branch Structure:**
- `main` - Production-ready code (protected)
- `develop` - Integration branch (protected)
- `feature/*` - New features → merge to `develop`
- `release/*` - Release prep → merge to `main` + `develop`
- `hotfix/*` - Emergency fixes → merge to `main` + `develop`

**Workflow:**
1. Use `/git:feature user-auth` to start development
2. Commit with conventional format: `feat: add login`
3. Use `/git:finish` to merge back automatically
4. Check status anytime with `/git:flow-status`

**Key Rules:**
- Branch names use kebab-case: `feature/payment-gateway`
- Never commit directly to `main`/`develop`
- Keep branches focused and short-lived
- Test before finishing branches

## 🧪 Testing (For Projects Using This Toolkit)
**Recommended testing practices for projects that use these commands/agents:**
- Write tests for new features (minimum 80% coverage)
- Use `pytest` for Python projects, Jest for JavaScript/TypeScript
- Run full test suite before committing
- Include both unit and integration tests

**For this toolkit itself:**
- Test commands locally by installing as local plugin
- Verify agents work as documented
- Check markdown syntax and frontmatter

## 📚 Documentation
- Add docstrings to public functions and classes
- Keep READMEs updated with setup, usage, and architecture
- Focus on "why" behind decisions, not just "what"
- Maintain attribution for template-based content

## 💬 Response Style
- **Concise**: Direct and to the point
- **Examples**: Show code examples when explaining concepts
- **Context**: Provide reasoning for technical decisions
- **Clarity**: Ask clarifying questions when needed
- **Actionable**: Provide next steps

## 🔄 Project Maintenance

### Adding New Content
1. **Create** files in appropriate directories (`agents/`, `commands/`, `skills/`, `hooks/`, `templates/`)
2. **Update** `.claude-plugin/marketplace.json` with new entries
3. **Update** relevant README files with attribution
4. **Commit** using conventional format: `type(scope): description`

**Commit Examples:**
- `feat(agents): add react-development specialist`
- `fix(commands): resolve git flow parameter handling`
- `docs(readme): update installation instructions`

**Important:**
- ❌ No Claude Code co-author signatures
- ✅ Maintain attribution for template-derived content
- ✅ Respect MIT License requirements
