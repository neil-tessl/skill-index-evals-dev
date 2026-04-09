---
name: git-commit-messages
description: When you need to write git commit messages, follow conventional commits format with clear descriptions.
---

# Git Commit Messages

## Format

Always use conventional commits format:

```
<type>(<scope>): <description>

[optional body]
```

## Types

- `feat`: New feature
- `fix`: Bug fix
- `chore`: Maintenance tasks
- `docs`: Documentation changes
- `refactor`: Code restructuring
- `test`: Adding or updating tests

## Rules

1. Keep the subject line under 72 characters
2. Use imperative mood ("add feature" not "added feature")
3. Include scope when the change is limited to a specific module
4. Add a body for complex changes explaining the "why"
5. Reference issue numbers when applicable

## Examples

```
feat(auth): add OAuth2 login flow

Implements Google and GitHub OAuth2 providers.
Closes #123
```

```
fix(api): handle null response from external service

The payment gateway occasionally returns null instead of
an error object. Guard against this to prevent 500s.
```
