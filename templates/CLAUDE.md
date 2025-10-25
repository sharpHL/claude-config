# Project Configuration Template

Use this template as a starting point for your project's `.claude/CLAUDE.md` file.

---

# Project: [Your Project Name]

## Overview
[Brief description of what this project does and its main purpose]

## Technology Stack
- **Language**: [e.g., TypeScript, Python, Go]
- **Framework**: [e.g., React, Express, FastAPI]
- **Database**: [e.g., PostgreSQL, MongoDB]
- **Testing**: [e.g., Jest, Pytest]
- **Build Tool**: [e.g., Webpack, Vite]

## Architecture
[Describe the high-level architecture]

### Key Directories
- `src/` - [Source code description]
- `tests/` - [Test organization]
- `docs/` - [Documentation]
- `scripts/` - [Build and deployment scripts]

### Design Patterns
[List main design patterns used, e.g., MVC, Repository Pattern, etc.]

## Coding Standards

### General Principles
- Follow [Style Guide Name, e.g., Airbnb, PEP 8]
- Maximum function length: [e.g., 50 lines]
- Maximum file length: [e.g., 300 lines]
- Use meaningful variable names
- Prefer composition over inheritance

### Language-Specific
```typescript
// TypeScript example
- Use strict mode
- Explicit return types for functions
- Prefer interfaces over type aliases for objects
- Use const for immutable values
```

### File Naming
- Components: `PascalCase.tsx`
- Utilities: `camelCase.ts`
- Tests: `*.test.ts` or `*.spec.ts`
- Constants: `UPPER_SNAKE_CASE.ts`

## Testing Strategy

### Coverage Requirements
- Minimum coverage: [e.g., 80%]
- Required for: [e.g., all business logic, API endpoints]

### Test Organization
```
tests/
├── unit/         # Unit tests
├── integration/  # Integration tests
└── e2e/         # End-to-end tests
```

### Running Tests
```bash
# All tests
npm test

# Watch mode
npm test -- --watch

# Coverage
npm test -- --coverage
```

## Development Workflow

### Getting Started
```bash
# Install dependencies
npm install

# Set up environment
cp .env.example .env

# Run database migrations
npm run migrate

# Start development server
npm run dev
```

### Common Commands
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run test` - Run tests
- `npm run lint` - Run linter
- `npm run format` - Format code

### Git Workflow
1. Create feature branch from `main`
2. Make changes
3. Write/update tests
4. Run linter and tests locally
5. Commit with conventional commit message
6. Push and create PR
7. Request code review
8. Merge after approval

### Commit Message Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

Types: feat, fix, docs, style, refactor, test, chore

## Code Review Checklist
- [ ] Tests pass
- [ ] Code follows style guide
- [ ] No hardcoded secrets
- [ ] Error handling implemented
- [ ] Documentation updated
- [ ] No console.logs in production code
- [ ] Types are properly defined (TypeScript)

## Security Guidelines
- Never commit `.env` files
- Use environment variables for secrets
- Validate all user input
- Sanitize data before database queries
- Use parameterized queries
- Implement rate limiting on APIs
- Keep dependencies updated

## Performance Considerations
- Optimize database queries (use indexes)
- Implement caching where appropriate
- Lazy load large components
- Use pagination for large datasets
- Minimize bundle size
- Optimize images

## Deployment

### Environments
- **Development**: [URL or description]
- **Staging**: [URL or description]
- **Production**: [URL or description]

### Deployment Process
1. [Step 1]
2. [Step 2]
3. [Step 3]

### Environment Variables
```bash
# Required
DATABASE_URL=
API_KEY=
SECRET_KEY=

# Optional
REDIS_URL=
FEATURE_FLAG_X=
```

## Troubleshooting

### Common Issues
**Issue**: [Common problem]
**Solution**: [How to fix it]

**Issue**: [Another common problem]
**Solution**: [How to fix it]

### Getting Help
- Check `docs/` for detailed documentation
- Search existing issues on GitHub
- Ask in team chat
- Contact: [maintainer email]

## API Documentation
[Link to API docs or brief description of endpoints]

## Dependencies

### Key Dependencies
- [Dependency 1]: [Purpose]
- [Dependency 2]: [Purpose]

### Updating Dependencies
```bash
# Check for updates
npm outdated

# Update dependencies
npm update

# Check for vulnerabilities
npm audit
```

## Resources
- [Project Documentation](link)
- [Design System](link)
- [API Reference](link)
- [Contributing Guide](link)

## Team Preferences

### Claude Code Usage
- Use `/analyze-project` before starting major refactors
- Run `/security-audit` before each release
- Use code-review-specialist agent for all PRs
- Create slash commands for repeated workflows

### Communication
- Async-first communication
- Document decisions in [location]
- Weekly sync meetings on [day]

---

**Last Updated**: [Date]
**Maintained By**: [Team/Person]
