---
name: python-optimizer
description: Automatically optimize Python code when user asks for performance improvements, code review, or refactoring. Focuses on async patterns, type hints, and modern Python idioms.
allowed-tools:
  - Read
  - Edit
  - Grep
---

# Python Code Optimizer

Automatically activate when:
- User mentions "optimize", "improve", "refactor" Python code
- User asks for code review of Python files
- User complains about slow Python code
- User wants to convert sync to async

## Optimization Checklist

### 1. Type Hints
- Add type hints to all function parameters and returns
- Use `list[str]` instead of `List[str]` (Python 3.9+)
- Use `X | None` instead of `Optional[X]` (Python 3.10+)

### 2. Async I/O
Identify and convert blocking operations:
| Blocking | Async Alternative |
|----------|-------------------|
| `requests` | `aiohttp` |
| `open()` | `aiofiles.open()` |
| `time.sleep()` | `asyncio.sleep()` |
| `psycopg2` | `asyncpg` |

### 3. Performance Patterns
```python
# List comprehension > map/filter
[x * 2 for x in items]  # ✅

# Generator for large data
(process(x) for x in huge_list)  # ✅

# dict.get() with default
value = d.get("key", default)  # ✅

# Use sets for membership
if item in set_of_items:  # ✅ O(1)

# functools.lru_cache for expensive functions
@lru_cache(maxsize=128)
def expensive(n: int) -> int: ...
```

### 4. Modern Idioms
```python
# Walrus operator (3.8+)
if (n := len(data)) > 10:
    print(f"Large: {n}")

# f-strings > .format()
f"Hello {name}"  # ✅

# Pathlib > os.path
from pathlib import Path
path = Path("dir") / "file.txt"

# dataclasses for data containers
@dataclass
class User:
    name: str
    age: int
```

## Output Format

When optimizing, provide:

```
🔧 Python Optimization

📊 Analysis:
- Type coverage: X%
- Blocking calls: N found
- Complexity issues: N found

🎯 Changes:
1. [file:line] Added type hints
2. [file:line] Converted to async
3. [file:line] Simplified logic

📈 Impact:
- Type safety: improved
- Performance: ~Nx faster (for I/O bound)
- Readability: improved
```
