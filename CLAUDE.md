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
- **Commit Messages**: Use conventional commits format
  - `feat:` - New features
  - `fix:` - Bug fixes
  - `docs:` - Documentation changes
  - `refactor:` - Code refactoring
  - `test:` - Test additions/changes
  - `chore:` - Maintenance tasks
- **Branching**: Create feature branches from `main`/`master`
- **Quality**: Always run tests before committing
- **Tools**: Prefer Git CLI over GUI tools

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
