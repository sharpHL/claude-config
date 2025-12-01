---
allowed-tools: Bash(git:*), Read
description: Display comprehensive Git Flow status including branch type, sync status, changes, and merge targets
source: https://github.com/davila7/claude-code-templates (MIT License, Author: Daniel Avila)
---

# Git Flow Status

Display comprehensive Git Flow repository status

## Current Repository State

- Current branch: !`git branch --show-current`
- Git status: !`git status --porcelain`
- Branch list: !`git branch -a | grep -E '(feature|release|hotfix|develop|main)' | head -20`
- Latest tags: !`git tag --sort=-version:refname | head -5`
- Recent commits: !`git log --oneline --graph --all -10`
- Remote status: !`git remote -v`

## Task

Provide a comprehensive Git Flow status report:

### 1. Branch Analysis

Determine current branch type:

| Branch | Type | Icon |
|--------|------|------|
| main | Production | 🏠 |
| develop | Integration | 🔀 |
| feature/* | Feature | 🌿 |
| release/* | Release | 🚀 |
| hotfix/* | Hotfix | 🔥 |

### 2. Status Display

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🌿 GIT FLOW STATUS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📍 CURRENT BRANCH
   [icon] [branch name]
   Type: [branch type]
   Base: [origin branch]
   Target: [merge destination]

📊 REPOSITORY INFO
   Remote: origin
   Latest tag: v1.2.0
   Active features: N
   Active releases: N
   Active hotfixes: N

🔄 SYNC STATUS
   Commits ahead: ↑ N
   Commits behind: ↓ N

📝 WORKING DIRECTORY
   Modified: N files
   Added: N files
   Untracked: N files

🎯 MERGE TARGET
   Will merge to: [target branch]
   Merge status: [Ready/Conflicts]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### 3. Recommendations

Provide actionable recommendations based on status:

```
💡 RECOMMENDATIONS

Priority Actions:
  1. [Action items based on current state]

Next Steps:
  [Suggested commands]
```

### 4. All Git Flow Branches

List all active Git Flow branches:

```
📋 ACTIVE BRANCHES

🌿 Features:
  feature/xxx (N commits, N days old)

🚀 Releases:
  release/vX.Y.Z (N commits)

🔥 Hotfixes:
  hotfix/xxx (N commits)

🏠 Main branches:
  main (production)
  develop (integration)
```

## Related Commands

- `/feature <name>` - Create feature branch
- `/release <version>` - Create release branch
- `/hotfix <name>` - Create hotfix branch
- `/finish` - Complete current branch
