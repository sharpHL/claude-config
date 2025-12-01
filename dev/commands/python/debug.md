---
allowed-tools: Read, Grep, Glob, Bash
argument-hint: [error message or file:line]
description: Analyze Python errors, find root cause, and suggest fixes
---

# Python Debug

Analyze: **$ARGUMENTS**

## Current Context

- Recent error: !`cat /tmp/pytest_output.txt 2>/dev/null | tail -50 || echo "No recent test output"`
- Python version: !`python --version 2>/dev/null`
- Working directory: !`pwd`

## Task

Analyze the error and provide actionable fixes.

### 1. Error Classification

Identify error type:

| Type | Common Causes |
|------|---------------|
| `ImportError` | Missing dep, wrong path, circular import |
| `TypeError` | Wrong argument type, None operations |
| `AttributeError` | Missing attr, None access, typo |
| `KeyError` | Missing dict key, wrong key name |
| `ValueError` | Invalid value, parsing failure |
| `AsyncioError` | Missing await, wrong event loop |
| `SQLAlchemyError` | DB connection, query syntax, session issues |

### 2. Analysis Steps

1. **Parse the traceback**
   - Identify the exception type
   - Find the originating file and line
   - Trace the call stack

2. **Read the relevant code**
   - The line that raised the exception
   - Surrounding context (5-10 lines)
   - Related function definitions

3. **Identify root cause**
   - Is it a typo?
   - Missing import/dependency?
   - Type mismatch?
   - Async/await issue?
   - Configuration problem?

4. **Check common issues**
   ```python
   # Async issues
   await missing_await()  # forgot await
   async def in sync context  # wrong context

   # Type issues
   None.attribute  # NoneType has no attribute
   str + int  # can't concatenate

   # Import issues
   from module import missing  # doesn't exist
   circular imports  # A imports B imports A
   ```

### 3. Output Format

```
🔍 Error Analysis

📛 Exception: [ExceptionType]
📍 Location: [file:line]
💬 Message: [error message]

🔗 Call Stack:
  1. [file:line] function_name()
  2. [file:line] another_function()
  → [file:line] failing_line()  ← Error here

🎯 Root Cause:
[Clear explanation of why this error occurred]

✅ Fix:
[Specific code change to fix the issue]

```python
# Before (broken)
[problematic code]

# After (fixed)
[corrected code]
```

💡 Prevention:
[How to avoid this error in the future]
```

### 4. Common Fixes

**ImportError: No module named 'xxx'**
```bash
uv add xxx
```

**ModuleNotFoundError with local module**
```bash
# Check PYTHONPATH or use:
uv run python -m module.submodule
```

**TypeError: object is not callable**
```python
# Check if you're using () on a non-function
# Or shadowing a function name with a variable
```

**AttributeError: 'NoneType' has no attribute**
```python
# Add null check
if obj is not None:
    obj.attribute

# Or use optional chaining pattern
result = obj.attribute if obj else default
```

**async/await issues**
```python
# Missing await
result = await async_function()  # Add await

# Sync function calling async
async def wrapper():
    return await async_function()
asyncio.run(wrapper())
```

### 5. Run Diagnostics

If error is unclear, run:

```bash
# Check imports
uv run python -c "import module_name"

# Check syntax
uv run python -m py_compile file.py

# Verbose pytest
uv run pytest -v --tb=long

# Type check
uv run mypy file.py --show-error-codes
```

### 6. Interactive Debug

Suggest debug strategies:

```python
# Add breakpoint
breakpoint()  # Python 3.7+

# Or use print debugging
print(f"DEBUG: {variable=}")

# Or logging
import logging
logging.basicConfig(level=logging.DEBUG)
logging.debug(f"Variable state: {var}")
```
