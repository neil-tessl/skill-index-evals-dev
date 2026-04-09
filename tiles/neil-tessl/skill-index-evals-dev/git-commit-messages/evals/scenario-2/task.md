# Changelog Generation from Change Descriptions

## Problem/Feature Description

Your open source project uses an automated tool to generate changelogs from the git history. The tool parses each commit message to categorize changes by type and module, and extracts issue/PR references to build links in the release notes. The tool expects commits to be consistently structured to function correctly.

Before cutting the v2.3.0 release, your team needs to turn a set of informal change descriptions (written as internal notes) into proper git commit messages. Some of these changes are tied to GitHub issues that must be referenced in the resulting commits so the changelog tool can link to them. Others span multiple files but are scoped to a single subsystem.

Your task is to write the commit message for each change below. Save all messages in a file called `release_commits.md`.

## Changes to Document

1. **Issue #88** — The CSV export function in the reporting module was exporting dates in MM/DD/YYYY format instead of ISO 8601. Users in non-US locales were getting malformed files. This is now fixed.

2. **Issue #91** — Added the ability for admin users to bulk-archive projects from the dashboard. The feature adds a new endpoint and updates the project list UI component.

3. **(no issue)** — Moved all database query helper functions out of `utils.py` into a new `db/queries.py` module. No behaviour was changed; this is purely structural cleanup to make the codebase easier to navigate.

4. **Issue #95** — The CI pipeline was failing intermittently because the test suite spun up a real Redis instance and occasionally hit port conflicts in the shared runner environment. The tests were updated to use a mock Redis adapter instead.

5. **(no issue)** — Updated `CONTRIBUTING.md` to explain the new branch naming convention introduced last month and added a section on how to run integration tests locally.
