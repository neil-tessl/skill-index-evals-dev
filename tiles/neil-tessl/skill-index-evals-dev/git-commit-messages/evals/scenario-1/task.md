# Document a Feature Branch for Code Review

## Problem/Feature Description

Your team is finishing up a sprint and preparing a feature branch for code review before merging into main. The branch contains several commits covering different aspects of a new user notification system. The engineering manager wants to make sure the git history is clean and informative before the branch is merged, since the project follows a squash-and-merge policy only for hotfixes — regular features keep their individual commit history.

You've been asked to write the commit messages for this feature branch. Each message must stand on its own and help a future developer understand what was done and — where relevant — why it was done that way.

## Output Specification

Create a file called `commit_messages.md` containing one commit message per change listed below. Each commit message should be complete and ready to paste into `git commit`.

## Changes to Document

1. **Notification service**: A new background service was added that polls for pending notifications every 30 seconds and dispatches email and push events. The 30-second interval was chosen after load testing showed that shorter intervals caused spikes in database connections.

2. **User preferences schema**: The `users` table gained three new nullable columns: `notify_email` (boolean), `notify_push` (boolean), and `notification_frequency` (enum: immediate, digest). These were made nullable for backwards compatibility with existing rows.

3. **Notification templates**: Six new HTML email templates were added under `templates/notifications/`. These are Jinja2 templates following the team's existing template conventions.

4. **Bug fix in email sender**: A race condition in the existing email sender was discovered and fixed while working on this feature. When two threads called `flush()` simultaneously, the internal buffer could be written twice, sending duplicate emails.

5. **Tests for notification service**: Unit and integration tests covering the new notification service were added, including mocks for the email and push adapters.
