---
allowed-tools: Read, Grep, Glob, Bash
argument-hint: [file|directory]
description: Review Python code for type hints, async patterns, security, and best practices
---

# Python Code Review

Review: **$ARGUMENTS**

If no path specified, review changed files: !`git diff --name-only HEAD 2>/dev/null | grep '\.py$' | head -10`

## Current State

- Python files: !`find . -name "*.py" -not -path "./.venv/*" 2>/dev/null | wc -l | tr -d ' '`
- Type checking: !`uv run mypy --version 2>/dev/null && echo "available" || echo "not installed"`
- Linting: !`uv run ruff --version 2>/dev/null && echo "available" || echo "not installed"`

## Review Checklist

### 1. Type Hints

Check every function has type annotations:

```python
# ❌ Missing types
def process(data, limit=10):
    return data[:limit]

# ✅ Complete types
def process(data: list[str], limit: int = 10) -> list[str]:
    return data[:limit]
```

Report:
- Functions without return type
- Parameters without type hints
- Use of `Any` without justification

### 2. Async Patterns

Identify blocking calls in async code:

| Blocking | Should Be |
|----------|-----------|
| `requests.get()` | `aiohttp` |
| `open()` | `aiofiles.open()` |
| `time.sleep()` | `asyncio.sleep()` |
| sync DB drivers | async drivers |

Check for:
- `await` in non-async functions
- Missing `async with` for context managers
- Sequential awaits that could be `gather()`

### 3. Security

- Hardcoded secrets, API keys, passwords
- SQL injection (string formatting in queries)
- Command injection (`subprocess` with `shell=True`)
- Unsafe deserialization (`pickle.loads`, `eval`)
- Missing input validation

### 4. Code Quality

- Unused imports
- Overly complex functions (cyclomatic complexity)
- Duplicate code
- Magic numbers without constants
- Missing docstrings on public functions
- Bare `except:` clauses

### 5. Dependencies

- Check if using `requests` (should be `aiohttp`)
- Check if using `pip` commands (should be `uv`)
- Outdated patterns (e.g., `Optional[X]` vs `X | None`)

## Output Format

```
📝 Python Code Review

📁 Files reviewed: X

## Type Coverage
✓ X/Y functions have complete type hints
⚠️ Missing types:
  - file.py:15 `process()` - missing return type
  - file.py:32 `fetch()` - parameter `url` untyped

## Async Issues
⚠️ Found X blocking calls:
  - file.py:45 `requests.get()` → use `aiohttp`
  - file.py:67 `time.sleep()` → use `asyncio.sleep()`

## Security
🔒 No issues found
  or
🚨 Found X issues:
  - file.py:12 Hardcoded API key
  - file.py:89 SQL injection risk

## Code Quality
- Unused imports: X
- Complex functions: X (>10 branches)
- Missing docstrings: X

## Summary
✓ Good: [positive points]
⚠️ Action needed: [priority fixes]
```

## Auto-fix

If `--fix` argument provided, automatically fix:
- Import sorting (`ruff check --select I --fix`)
- Simple type issues
- Unused imports (`ruff check --select F401 --fix`)

```bash
uv run ruff check . --fix
uv run ruff format .
```
