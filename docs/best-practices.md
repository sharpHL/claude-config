# Claude Code Best Practices

A collection of best practices for working effectively with Claude Code.

## 🎯 General Guidelines

### 1. Clear Communication
- **Be Specific**: Provide clear, specific instructions
- **Context Matters**: Share relevant context about your project
- **Ask Follow-ups**: Don't hesitate to ask for clarification

### 2. Effective Task Management
- **Break Down Tasks**: Large tasks into smaller, manageable pieces
- **Use Todo Lists**: Leverage the todo list feature for complex tasks
- **Iterative Approach**: Build and test incrementally

### 3. Code Quality
- **Request Reviews**: Use the code-review agent before merging
- **Write Tests**: Always ask for tests with new functionality
- **Document Changes**: Ensure documentation stays up-to-date

## 📁 Project Organization

### CLAUDE.md Files

Use `.claude/CLAUDE.md` files to provide project-specific context:

```markdown
# Project Context

## Overview
Brief description of what this project does

## Architecture
Key architectural decisions and patterns

## Coding Standards
- Use TypeScript strict mode
- Follow Airbnb style guide
- Maximum function length: 50 lines

## Testing Strategy
- Unit tests required for all business logic
- Integration tests for API endpoints
- E2E tests for critical user flows

## Common Tasks
- Build: npm run build
- Test: npm run test
- Deploy: npm run deploy:prod
```

### Slash Commands

Create project-specific slash commands for repeated workflows:

**Example: `.claude/commands/deploy.md`**
```markdown
---
description: Deploy application to production
---

Deploy the application following these steps:
1. Run all tests and ensure they pass
2. Build the production bundle
3. Run security audit
4. Deploy to staging first
5. Run smoke tests on staging
6. Deploy to production
7. Verify deployment with health checks
8. Monitor logs for 5 minutes
```

## 🔧 Tool Usage

### When to Use Different Tools

- **Grep**: Fast content searches across files
- **Glob**: Finding files by pattern
- **Read**: Reading specific files
- **Edit**: Precise changes to existing files
- **Write**: Creating new files (use sparingly)
- **Bash**: Running commands, tests, builds

### Search Strategies

```bash
# Find all API routes
Use Glob: **/routes/**/*.ts

# Find authentication logic
Use Grep: pattern="authenticate|auth" type="ts"

# Find all TODO comments
Use Grep: pattern="TODO|FIXME" output_mode="content"
```

## 🚀 Performance Tips

### 1. Efficient Context Usage
- Read files only once if possible
- Use Grep instead of reading all files
- Leverage parallel tool calls

### 2. Strategic Agent Usage
- Use specialized agents for complex tasks
- Let agents handle multi-step investigations
- Combine agent results for comprehensive analysis

### 3. Caching Strategies
- Reuse analysis results within a session
- Document findings for future reference
- Build knowledge incrementally

## 🔒 Security Practices

### 1. Sensitive Data
```markdown
Never commit to git:
- .env files
- API keys
- Credentials
- Private keys
- Database passwords
```

### 2. Code Review Checklist
- [ ] No hardcoded secrets
- [ ] Input validation implemented
- [ ] SQL injection prevention
- [ ] XSS protection
- [ ] Authentication checks
- [ ] Authorization verified

### 3. Dependency Management
```bash
# Regular security audits
npm audit
npm audit fix

# Keep dependencies updated
npm outdated
npm update
```

## 📝 Documentation Standards

### README Template
```markdown
# Project Name

## Overview
What this project does

## Installation
Step-by-step setup instructions

## Usage
How to use the project

## Configuration
Environment variables and settings

## Development
How to contribute

## Testing
How to run tests

## Deployment
Deployment instructions

## License
License information
```

### Code Documentation
```typescript
/**
 * Fetches user data from the API
 *
 * @param userId - The unique identifier for the user
 * @param options - Optional fetch configuration
 * @returns Promise resolving to user data
 * @throws {ApiError} When the API request fails
 *
 * @example
 * const user = await fetchUser('123', { cache: true });
 */
async function fetchUser(
  userId: string,
  options?: FetchOptions
): Promise<User> {
  // Implementation
}
```

## 🧪 Testing Best Practices

### Test Organization
```
tests/
├── unit/           # Unit tests
├── integration/    # Integration tests
├── e2e/            # End-to-end tests
└── fixtures/       # Test data
```

### Test Naming
```typescript
describe('UserService', () => {
  describe('createUser', () => {
    it('should create a user with valid data', () => {});
    it('should throw error when email is invalid', () => {});
    it('should hash password before saving', () => {});
  });
});
```

## 🔄 Git Workflow

### Commit Messages
```
Type: Brief description

Detailed explanation if needed

- Bullet points for multiple changes
- Reference issue numbers: #123

Types: feat, fix, docs, style, refactor, test, chore
```

### Branch Naming
```
feature/user-authentication
fix/memory-leak-in-cache
refactor/api-error-handling
docs/update-readme
```

## 🎨 Code Style

### Consistency
- Use project's existing style
- Configure linters and formatters
- Run pre-commit hooks

### Readability
```typescript
// Good: Clear and descriptive
function calculateUserSubscriptionTotal(userId: string): number {
  const subscription = getUserSubscription(userId);
  return subscription.basePrice + subscription.addons.reduce(
    (total, addon) => total + addon.price,
    0
  );
}

// Bad: Unclear and abbreviated
function calcUST(uid: string): number {
  const sub = getUSub(uid);
  return sub.bp + sub.ao.reduce((t, a) => t + a.p, 0);
}
```

## 🔍 Debugging Tips

### Systematic Approach
1. **Reproduce**: Can you consistently reproduce the issue?
2. **Isolate**: Narrow down to the smallest test case
3. **Hypothesize**: What could cause this behavior?
4. **Test**: Verify your hypotheses
5. **Fix**: Implement the solution
6. **Verify**: Ensure the fix works and doesn't break other things

### Logging Strategy
```typescript
// Development: Detailed logging
console.log('User data:', JSON.stringify(user, null, 2));

// Production: Structured logging
logger.info('User authenticated', {
  userId: user.id,
  timestamp: Date.now()
});

// Error logging
logger.error('Authentication failed', {
  error: err.message,
  stack: err.stack,
  userId
});
```

## 📊 Performance Optimization

### Measurement First
```typescript
// Measure before optimizing
console.time('operation');
performExpensiveOperation();
console.timeEnd('operation');
```

### Common Optimizations
- Cache expensive computations
- Use appropriate data structures
- Implement lazy loading
- Optimize database queries
- Use pagination for large datasets
- Implement debouncing/throttling

## 🎓 Learning Resources

- [Claude Code Documentation](https://docs.claude.com/en/docs/claude-code)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [MDN Web Docs](https://developer.mozilla.org/)
- [OWASP Security Guide](https://owasp.org/)
- [Clean Code Principles](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)

---

**Remember**: These are guidelines, not strict rules. Adapt them to your project's needs.
