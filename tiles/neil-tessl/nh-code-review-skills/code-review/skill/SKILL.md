---
name: code-review
description: Perform thorough code reviews focusing on correctness, readability, and security.
---

# Code Review

## Review Checklist

1. **Correctness** - Does the code do what it claims?
2. **Edge cases** - Are boundary conditions handled?
3. **Security** - No injection, no leaked secrets, no unsafe deserialization
4. **Readability** - Clear names, small functions, minimal nesting
5. **Tests** - Are changes covered by tests?

## Feedback Style

- Lead with what works well
- Be specific: reference line numbers and suggest alternatives
- Distinguish blocking issues from nits
- One comment per concern

## Examples

### Blocking

> `fetchUser` doesn't handle the case where the API returns 404. This will throw an unhandled exception in production. Consider returning `null` and guarding the caller.

### Nit

> Nit: `data` is generic — `userProfile` would make the intent clearer.
