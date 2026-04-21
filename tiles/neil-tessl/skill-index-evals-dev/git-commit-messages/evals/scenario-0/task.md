# Prepare Commits for Code Review

## Problem Description

Your team is wrapping up a sprint and needs to push several staged changes to the main repository before a code review session this afternoon. The tech lead has asked everyone to make sure their commit history is clean and consistent so that reviewers can quickly understand the intent of each change without reading the diff in detail.

You have been handed a list of changes that need to be committed. For each change, write a well-formed commit message. All commit messages should go into a single file called `commit_messages.md`, with each message clearly labeled (e.g., "## Change 1", "## Change 2", etc.) and the full commit message text underneath.

## Output Specification

Produce a file named `commit_messages.md` containing a labeled commit message for each of the six changes below.

## Changes to Commit

**Change 1:** A new endpoint was added to the payments service that lets customers download their invoice as a PDF.

**Change 2:** A crash was fixed in the notification service — it was throwing an unhandled exception when a user's email address was missing from the database record.

**Change 3:** The README was updated to include a section on how to run the test suite locally.

**Change 4:** The user authentication logic was extracted into its own helper module to reduce duplication across three different route handlers.

**Change 5:** New unit tests were added for the cart pricing functions that were introduced last week.

**Change 6:** The build script was updated to delete the `dist/` directory before each production build to avoid stale artifacts.
