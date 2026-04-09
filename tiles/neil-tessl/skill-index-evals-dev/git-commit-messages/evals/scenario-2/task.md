# Standardizing Commit Messages for a New Contributor's PR

## Problem/Feature Description

A new engineer on your team has submitted a pull request containing five commits, but their commit messages don't meet the project's standards. Before the PR can be merged, you need to rewrite the commit messages to be consistent and informative. Your task is to propose a corrected commit message for each of the original ones.

The project has a mix of focused, single-module changes and broader cross-cutting changes — so some commits should identify which part of the codebase was affected, while others should not. Getting this distinction right is important: the team's release tooling parses commit messages to group changes by subsystem in the changelog.

Write a file called `rewritten_commits.md` with your proposed replacement for each commit message listed below. Label each one clearly (e.g., "## Commit A").

## Original Commit Messages to Rewrite

**Commit A** — Original: `"changes to the user authentication module"`
Context: Added password reset via email, touching only files under `src/auth/`.

**Commit B** — Original: `"Fixed stuff in DB layer"`
Context: Corrected an off-by-one error in the pagination query inside `src/db/`.

**Commit C** — Original: `"Updates"`
Context: Bumped the versions of three third-party libraries (requests, boto3, sqlalchemy) in `requirements.txt`, and updated two configuration defaults in `config/settings.py`, and revised the CI workflow in `.github/workflows/`. This touched many unrelated areas.

**Commit D** — Original: `"new background job processor"`
Context: Built the initial task queue worker, entirely within `src/task-queue/`.

**Commit E** — Original: `"Refactoring User Profile and Notification Services"`
Context: Extracted shared validation logic used by both `src/user-profile/` and `src/notifications/` into a new `src/shared/` module. This change spans multiple modules.
