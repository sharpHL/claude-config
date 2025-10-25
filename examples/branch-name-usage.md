# Branch Name Generator Usage Examples

This document demonstrates how to use the `/git:branch` command to generate Git Flow compliant branch names.

## Basic Usage

### Simple Feature Branch
```
Input: /git:branch "user authentication system"
Output: feature/user-authentication-system
```

### With Project Prefix
```
Input: /git:branch "payment integration" --project=ecommerce
Output: feature/ecommerce-payment-integration
```

### Different Branch Types

**Release Branch:**
```
Input: /git:branch "1.2.0" --type=release
Output: release/v1.2.0
```

**Hotfix Branch:**
```
Input: /git:branch "critical security patch" --type=hotfix
Output: hotfix/critical-security-patch
```

## Real-World Examples

### E-commerce Project
```
/git:branch "shopping cart redesign" --project=ecommerce
→ feature/ecommerce-shopping-cart-redesign

/git:branch "payment gateway api" --project=ecommerce
→ feature/ecommerce-payment-gateway-api
```

### Mobile App
```
/git:branch "push notifications" --project=mobile
→ feature/mobile-push-notifications

/git:branch "offline mode" --project=mobile
→ feature/mobile-offline-mode
```

### API Development
```
/git:branch "user authentication endpoint" --project=api
→ feature/api-user-authentication-endpoint

/git:branch "rate limiting" --project=api
→ feature/api-rate-limiting
```

## Integration with Git Flow

After getting a suggested branch name:

1. **Create the branch:**
   ```bash
   git checkout -b feature/user-authentication-system
   # Or use the Git Flow command:
   /feature user-authentication-system
   ```

2. **Check status:**
   ```bash
   /flow-status
   ```

3. **When done:**
   ```bash
   /finish
   ```

## Tips for Good Branch Names

1. **Be Specific:** "user login" is better than "auth"
2. **Use Context:** Include project or module when relevant
3. **Keep it Readable:** Avoid overly long or cryptic names
4. **Follow Patterns:** Consistent naming helps organization

## Common Patterns

| Type | Pattern | Example |
|------|---------|---------|
| Feature | `{project}-{feature}` | `ecommerce-payment-gateway` |
| Feature | `{module}-{action}` | `auth-user-login` |
| Release | `v{major}.{minor}.{patch}` | `v1.2.0` |
| Hotfix | `{issue}-{fix}` | `security-patch` |
| Hotfix | `{component}-bugfix` | `payment-bugfix` |