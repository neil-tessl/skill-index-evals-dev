# Commit Message Review and Rewrite

## Problem/Feature Description

Your team has just onboarded a new developer who submitted their first pull request. While reviewing the PR, you noticed their git commit history contains several commit messages that don't follow your team's established standards. The messages are inconsistent, making it difficult to understand what changed and why when scanning the git log.

The tech lead has asked you to produce a document that rewrites each commit into a well-structured message. The team relies on a consistent commit history to power automated changelog generation and release notes, so getting the format right is important.

## Output Specification

Create a file called `rewritten_commits.md` that contains:
1. Each original commit message (quoted)
2. The rewritten version below it
3. A brief note (1-2 sentences) explaining what you changed and why

The following commits need to be rewritten:

## Input Commits

```
1. "updated login page"
2. "fixed the bug where users couldn't reset password, also added some logging, closes #204"
3. "added unit tests for the payment module"
4. "refactoring database connection code"
5. "changed readme"
```
