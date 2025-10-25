---
allowed-tools: Bash(git:*), Read
argument-hint: <description> [--type=feature|release|hotfix] [--project=project-name]
description: Generate Git Flow compliant branch names based on description and type
---

# Git Flow Branch Generator

Generate compliant branch name for: **$ARGUMENTS**

## Current Repository State

- Current branch: !`git branch --show-current`
- Git status: !`git status --porcelain`
- Existing branches: !`git branch | grep -E '(feature|release|hotfix)' | head -10`

## Task

Generate a Git Flow compliant branch name based on your description:

### 1. Parse Arguments

Extract information from `$ARGUMENTS`:
- **Description**: Main functionality or feature description
- **Type**: Branch type (--type, defaults to "feature")
- **Project**: Optional project prefix (--project)

### 2. Generate Branch Name

Apply naming conventions:

```bash
# Convert description to kebab-case
DESCRIPTION=$(echo "$DESCRIPTION" | tr '[:upper:]' '[:lower:]' | sed 's/[^a-z0-9]/-/g' | sed 's/--*/-/g' | sed 's/^-\|-$//g')

# Add project prefix if specified
if [[ -n "$PROJECT" ]]; then
    BRANCH_NAME="${PROJECT}-${DESCRIPTION}"
else
    BRANCH_NAME="$DESCRIPTION"
fi

# Add Git Flow prefix
FINAL_NAME="${TYPE}/${BRANCH_NAME}"
```

### 3. Validate and Suggest

Check for conflicts and provide suggestions:

```
🌿 Suggested Branch Names:

Primary: $FINAL_NAME
✅ Follows Git Flow naming conventions
✅ Uses kebab-case format
✅ Descriptive and searchable

Alternative Options:
- $TYPE/$DESCRIPTION-short
- $TYPE/$DESCRIPTION-v2
- $TYPE/$DESCRIPTION-with-$CONTEXT
```

### 4. Examples by Type

**Feature Branches:**
```
Input: "user authentication system"
Output: feature/user-authentication-system

Input: "payment gateway integration" --project=ecommerce
Output: feature/ecommerce-payment-gateway-integration

Input: "dashboard redesign" --type=feature
Output: feature/dashboard-redesign
```

**Release Branches:**
```
Input: "1.2.0" --type=release
Output: release/v1.2.0

Input: "version 2.0 beta" --type=release
Output: release/v2.0.0-beta
```

**Hotfix Branches:**
```
Input: "critical security patch" --type=hotfix
Output: hotfix/critical-security-patch

Input: "payment failure fix" --type=hotfix
Output: hotfix/payment-failure-fix
```

### 5. Usage Integration

After getting the branch name, you can:

```bash
# Create the branch immediately
git checkout -b $SUGGESTED_NAME

# Or use with our Git Flow commands
/feature $BRANCH_BASE
/release $VERSION
/hotfix $HOTFIX_NAME
```

### 6. Naming Best Practices

**✅ Good Examples:**
- `feature/user-profile-page`
- `feature/api-v2-integration`
- `feature/payment-gateway`
- `release/v1.2.0`
- `hotfix/security-patch`

**❌ Avoid:**
- `feature/feat1`
- `feature/my_feature`
- `feature/Test Branch`
- Generic or unclear names

### 7. Conflict Detection

Check if suggested branch already exists:

```
⚠️  Branch 'feature/user-authentication' already exists

Existing branches:
  feature/user-authentication
  feature/user-profile
  feature/user-dashboard

Suggestions:
1. Use: feature/user-authentication-v2
2. Use: feature/user-auth-system
3. Use: feature/auth-user-flow
```

### 8. Quick Templates

Provide quick templates for common patterns:

**Authentication Features:**
- `feature/user-login`
- `feature/user-registration`
- `feature/password-reset`
- `feature/oauth-integration`

**API Features:**
- `feature/api-endpoint-create`
- `feature/api-response-format`
- `feature/api-v2-migration`
- `feature/api-authentication`

**UI Features:**
- `feature/dashboard-redesign`
- `feature/mobile-responsive`
- `feature/component-library`
- `feature/theme-system`

**Bug Fixes:**
- `hotfix/critical-security`
- `hotfix/payment-failure`
- `hotfix/memory-leak`
- `hotfix/performance-issue`

## Environment Variables

The command respects:
- `GIT_FLOW_DEFAULT_TYPE`: Default branch type (default: "feature")
- `GIT_FLOW_BRANCH_PREFIX`: Custom prefix logic
- `GIT_FLOW_MAX_LENGTH`: Maximum branch name length (default: 50)

## Related Commands

- `/git:feature <name>` - Create feature branch with suggested name
- `/git:release <version>` - Create release branch
- `/git:hotfix <name>` - Create hotfix branch
- `/git:flow-status` - Check current Git Flow status

## Tips

1. **Be Descriptive**: Include enough context in the name
2. **Use Consistent Patterns**: Follow team naming conventions
3. **Keep it Readable**: Avoid overly long or cryptic names
4. **Check Conflicts**: Verify the name doesn't already exist
5. **Think Future-Proof**: Names should make sense later

**Pro Tip**: Use this command before creating branches to ensure consistent naming across your project!