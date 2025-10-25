# User-Level Memory and Preferences

## 🌍 Language and Communication
**CRITICAL REQUIREMENT**: All responses, thoughts, code comments, and outputs MUST be in English, regardless of input language (including Chinese queries).

This applies to:
- Response messages and explanations
- Thinking/reasoning processes
- Code comments and documentation
- Output results and error messages
- Git commit messages

## 🐍 Python Development
**CRITICAL REQUIREMENT**: Use `uv` for all Python-related tasks instead of `pip`, `venv`, or other traditional tools.

`uv` handles:
- Python version management
- Package management
- Project initialization and management
- Virtual environment creation

**Tools:**
- Linting: `ruff`
- Formatting: `black` or `ruff format`

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

## 🔄 Git Workflow

### Git Flow Strategy
This project follows the Git Flow branching model with the following structure:

**Main Branches:**
- `main` - Production-ready code (protected, tagged releases)
- `develop` - Integration branch for features (protected)

**Supporting Branches:**
- `feature/*` - New features and enhancements
  - Branch from: `develop`
  - Merge back to: `develop`
  - Naming: `feature/<descriptive-name>` (kebab-case)
  - Examples: `feature/user-authentication`, `feature/payment-gateway`

- `release/*` - Release preparation
  - Branch from: `develop`
  - Merge to: `main` AND `develop`
  - Naming: `release/<version>` (e.g., `release/v1.2.0`)
  - Creates version tag on `main`

- `hotfix/*` - Emergency production fixes
  - Branch from: `main`
  - Merge to: `main` AND `develop`
  - Naming: `hotfix/<descriptive-name>` (kebab-case)
  - Examples: `hotfix/critical-security-patch`, `hotfix/payment-failure`
  - Creates patch version tag (e.g., v1.2.0 → v1.2.1)

**Available Commands:**
- `/feature <name>` - Create new feature branch from develop
- `/release <version>` - Create new release branch from develop
- `/hotfix <name>` - Create emergency hotfix branch from main
- `/finish` - Complete and merge current Git Flow branch
- `/flow-status` - Display comprehensive Git Flow status

**Commit Message Format:**
Use conventional commits format:
- `feat:` - New features
- `fix:` - Bug fixes
- `docs:` - Documentation changes
- `refactor:` - Code refactoring
- `test:` - Test additions/changes
- `chore:` - Maintenance tasks
- `perf:` - Performance improvements

**Branch Naming Rules:**
- Use kebab-case (lowercase-with-hyphens)
- Be descriptive and concise
- Avoid generic names like `feature1`, `fix`, `update`
- ✅ Good: `feature/user-profile-page`, `hotfix/auth-bypass-fix`
- ❌ Bad: `feat1`, `My_Feature`, `fix`

**Workflow Best Practices:**
- Keep feature branches short-lived and focused
- Push to remote regularly to avoid conflicts
- Run tests before finishing branches
- Never commit directly to `main` or `develop`
- Update CHANGELOG.md for releases
- Create tags for all releases and hotfixes
- Use `/finish` command for proper merge and cleanup

## 🧪 Testing
- Write tests for all new features
- Maintain minimum 80% test coverage
- Use `pytest` for Python projects
- Run full test suite before committing changes
- Include both unit and integration tests where appropriate

## 📚 Documentation
- Add docstrings to all public functions and classes
- Keep `README.md` updated with:
  - Setup and installation instructions
  - Usage examples
  - Project overview and architecture
- Document API endpoints with request/response examples
- Focus on explaining the "why" behind decisions, not just the "what"

## 💬 Response Style
- **Conciseness**: Be direct and to the point
- **Examples**: Show code examples when explaining concepts
- **Context**: Provide reasoning and context for technical decisions
- **Clarity**: Ask clarifying questions when requirements are ambiguous
- **Actionability**: Provide actionable next steps
