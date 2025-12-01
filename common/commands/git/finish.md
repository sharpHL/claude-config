---
allowed-tools: Bash(git:*), Read, Edit
argument-hint: [--no-delete] [--no-tag]
description: Complete and merge current Git Flow branch (feature/release/hotfix) with proper cleanup and tagging
source: https://github.com/davila7/claude-code-templates (MIT License, Author: Daniel Avila)
---

# Git Flow Finish Branch

Complete current Git Flow branch: **$ARGUMENTS**

## Current Repository State

- Current branch: !`git branch --show-current`
- Branch type: !`git branch --show-current | grep -oE '^(feature|release|hotfix)' || echo "Not a Git Flow branch"`
- Git status: !`git status --porcelain`
- Unpushed commits: !`git log @{u}.. --oneline 2>/dev/null | wc -l | tr -d ' '`
- Latest tag: !`git describe --tags --abbrev=0 2>/dev/null || echo "No tags"`

## Task

Complete the current Git Flow branch by merging it to appropriate target branch(es):

### 1. Branch Type Detection

| Branch Type | Merge To | Create Tag |
|-------------|----------|------------|
| feature/* | develop only | No |
| release/* | main AND develop | Yes (version) |
| hotfix/* | main AND develop | Yes (patch version) |

### 2. Pre-Merge Validation

- All changes are committed
- All commits are pushed to remote
- Tests are passing
- No merge conflicts with target branch

### 3. Feature Branch Finish

```bash
git push
git checkout develop
git pull origin develop
git merge --no-ff feature/$NAME -m "Merge feature/$NAME into develop"
git push origin develop
git branch -d feature/$NAME
git push origin --delete feature/$NAME
```

### 4. Release Branch Finish

```bash
git push
git checkout main
git pull origin main
git merge --no-ff release/$VERSION
git tag -a $VERSION -m "Release $VERSION"
git push origin main --tags
git checkout develop
git merge --no-ff release/$VERSION
git push origin develop
git branch -d release/$VERSION
git push origin --delete release/$VERSION
```

### 5. Hotfix Branch Finish

```bash
git push
git checkout main
git merge --no-ff hotfix/$NAME
git tag -a $NEW_VERSION -m "Hotfix $NEW_VERSION"
git push origin main --tags
git checkout develop
git merge --no-ff hotfix/$NAME
git push origin develop
git branch -d hotfix/$NAME
git push origin --delete hotfix/$NAME
```

### 6. Arguments

- `--no-delete`: Keep branch after merging
- `--no-tag`: Skip tag creation (release/hotfix only)

### 7. Error Handling

**Not on Git Flow Branch:**
```
❌ Not on a Git Flow branch

/finish only works on:
- feature/* branches
- release/* branches
- hotfix/* branches
```

**Uncommitted Changes:**
```
❌ Cannot finish: Uncommitted changes detected

Please commit or stash your changes first.
```

**Test Failures:**
```
❌ Cannot finish: Tests are failing

Fix the failing tests before finishing.
```

## Related Commands

- `/feature <name>` - Start new feature branch
- `/release <version>` - Start new release branch
- `/hotfix <name>` - Start new hotfix branch
- `/flow-status` - Check Git Flow status
