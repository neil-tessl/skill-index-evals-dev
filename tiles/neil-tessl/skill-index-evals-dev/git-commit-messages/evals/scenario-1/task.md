# Write Commit Messages for a Mixed Batch of Changes

## Problem Description

A backend engineering team is preparing a release branch for a microservices application. The codebase is organized into several top-level directories: `auth/`, `api/`, `db/`, `user-profile/`, and `email-sender/`. Each directory represents a self-contained service module.

During the release prep, several changes were made and need to be committed. Some changes are neatly isolated to one module, while others touched shared infrastructure or config files across the entire project.

The tech lead has asked for clean, professional commit messages that will hold up in code review and remain useful for future contributors navigating the git log.

Write commit messages for all five changes listed below, and save them to a file called `commit_messages.md`. Label each entry (e.g., "## Change 1") and include the full commit message text underneath.

## Output Specification

Produce a file named `commit_messages.md` with a labeled commit message for each of the five changes below.

## Changes to Commit

**Change 1:** Added rate limiting to the API gateway endpoints so that individual IP addresses cannot make more than 100 requests per minute.

**Change 2:** The password hashing algorithm in the authentication module was upgraded from MD5 to bcrypt to improve security.

**Change 3:** Updated ESLint rules, Prettier configuration, and the root-level `.editorconfig` file to enforce a consistent code style across all modules in the monorepo.

**Change 4:** Fixed a connection pool exhaustion bug in the database module that caused timeouts under load testing.

**Change 5:** Added a new `user-profile` service endpoint that returns the user's full activity history as a paginated JSON response. This is a new capability that did not previously exist in the user-profile module.
