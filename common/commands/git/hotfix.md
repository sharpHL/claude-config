---
allowed-tools: Bash(git:*), Read, Edit, Write
argument-hint: <hotfix-name>
description: Create a new Git Flow hotfix branch from main for emergency production fixes
source: https://github.com/davila7/claude-code-templates (MIT License, Author: Daniel Avila)
---

# Git Flow Hotfix Branch

Create emergency hotfix branch: **$ARGUMENTS**

## Current Repository State

- Current branch: !`git branch --show-current`
- Git status: !`git status --porcelain`
- Latest production tag: !`git describe --tags --abbrev=0 origin/main 2>/dev/null || echo "No tags on main"`

## Task

Create a Git Flow hotfix branch for emergency production fixes:

### 1. Pre-Flight Validation

**Critical Checks:**
- **Verify hotfix name**: Ensure `$ARGUMENTS` is provided and descriptive
  - Valid: `critical-security-patch`, `payment-gateway-fix`, `auth-bypass-fix`
  - Invalid: `fix`, `hotfix1`, `bug`
- **Check main branch exists**: Ensure `main` branch is present
- **Verify no uncommitted changes**: Clean working directory required

**⚠️ Hotfixes are ONLY for:**
- Critical security vulnerabilities
- Production-breaking bugs
- Payment/transaction failures
- Data loss or corruption issues

**NOT for:**
- Regular bug fixes (use feature branch)
- New features (use feature branch)
- Performance improvements (use feature branch)

### 2. Create Hotfix Branch Workflow

```bash
# Switch to main branch
git checkout main

# Pull latest production code
git pull origin main

# Create hotfix branch from main
git checkout -b hotfix/$ARGUMENTS

# Set up remote tracking
git push -u origin hotfix/$ARGUMENTS
```

### 3. Version Bump

Hotfix version: Always increment PATCH (X.Y.Z → X.Y.Z+1)
- v1.2.0 → v1.2.1
- v2.0.5 → v2.0.6

### 4. Success Response

```
✓ Created branch: hotfix/$ARGUMENTS
✓ Set up remote tracking

🔥 Hotfix Branch Ready: hotfix/$ARGUMENTS

Branch: hotfix/$ARGUMENTS
Base: main (production)
Will merge to: main AND develop
Suggested version: v1.2.1

⚠️ CRITICAL HOTFIX WORKFLOW

1. 🔍 Identify the Issue
2. 🛠️ Implement the Fix (MINIMAL changes)
3. 🧪 Test Thoroughly
4. 📝 Document the Fix
5. 🚀 Deploy Process

🎯 Next Steps:
1. Fix the critical issue (MINIMAL changes only)
2. Test thoroughly
3. Create emergency PR
4. Run /finish to merge to main AND develop
5. Deploy to production immediately
```

## Related Commands

- `/finish` - Complete hotfix (merge to main and develop, create tag)
- `/flow-status` - Check current Git Flow status
- `/feature <name>` - Create feature branch (for non-critical fixes)
- `/release <version>` - Create release branch
