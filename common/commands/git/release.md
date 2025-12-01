---
allowed-tools: Bash(git:*), Read, Edit, Write
argument-hint: <version>
description: Create a new Git Flow release branch from develop with version bumping and changelog generation
source: https://github.com/davila7/claude-code-templates (MIT License, Author: Daniel Avila)
---

# Git Flow Release Branch

Create new release branch: **$ARGUMENTS**

## Current Repository State

- Current branch: !`git branch --show-current`
- Git status: !`git status --porcelain`
- Latest tag: !`git describe --tags --abbrev=0 2>/dev/null || echo "No tags found"`
- Commits since last tag: !`git log $(git describe --tags --abbrev=0 2>/dev/null)..HEAD --oneline 2>/dev/null | wc -l | tr -d ' '`
- Recent commits: !`git log --oneline -10`

## Task

Create a Git Flow release branch following these steps:

### 1. Version Validation

**Version Format Requirements:**
- Must follow semantic versioning: `vMAJOR.MINOR.PATCH`
- Examples: `v1.0.0`, `v2.1.3`, `v0.5.0-beta.1`

**Version Increment Logic:**
- **MAJOR** (v2.0.0): Breaking changes (contains "BREAKING CHANGE:" in commits)
- **MINOR** (v1.3.0): New features (contains "feat:" commits)
- **PATCH** (v1.2.1): Bug fixes only (only "fix:" and "chore:" commits)

### 2. Create Release Branch Workflow

```bash
# Switch to develop and update
git checkout develop
git pull origin develop

# Create release branch
git checkout -b release/$ARGUMENTS

# Update package.json version (if Node.js project)
npm version ${ARGUMENTS#v} --no-git-tag-version

# Commit version bump
git add package.json CHANGELOG.md
git commit -m "chore(release): bump version to ${ARGUMENTS#v}"

# Push to remote with tracking
git push -u origin release/$ARGUMENTS
```

### 3. CHANGELOG Generation

Generate changelog from commits since last tag, grouped by type:

```markdown
# Changelog

## [$ARGUMENTS] - [Current Date]

### Features
- [List all feat: commits]

### Bug Fixes
- [List all fix: commits]

### Breaking Changes
- [List all commits with BREAKING CHANGE]
```

### 4. Success Response

```
✓ Created branch: release/$ARGUMENTS
✓ Updated package.json version
✓ Generated CHANGELOG.md
✓ Pushed branch to remote

🚀 Release Branch Ready: $ARGUMENTS

🎯 Next Steps:
1. Review CHANGELOG.md for accuracy
2. Run final tests: npm test
3. Create PR to main: gh pr create
4. Get team approvals
5. Run /finish to complete release
```

### 5. Error Handling

**Invalid Version Format:**
```
❌ Invalid version format: "$ARGUMENTS"

✅ Use semantic versioning: vMAJOR.MINOR.PATCH

Examples:
  - v1.0.0 (initial release)
  - v1.2.0 (new features)
  - v1.2.1 (bug fixes)
```

## Related Commands

- `/finish` - Complete release (merge to main and develop, create tag)
- `/flow-status` - Check current Git Flow status
- `/feature <name>` - Create feature branch
- `/hotfix <name>` - Create hotfix branch
