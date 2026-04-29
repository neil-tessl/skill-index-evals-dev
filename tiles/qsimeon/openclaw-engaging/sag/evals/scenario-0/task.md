# Product Launch Announcement TTS Script

## Problem/Feature Description

Your company is launching a new developer tool called "OpenClaw SDK v2.5" and the marketing team needs a polished audio announcement to play at the upcoming keynote. The announcement contains a mix of technical product names, version numbers, URLs (like https://openclaw.dev/docs), and metric figures (e.g., "99.9% uptime", "2.5x faster"). Previous automated attempts produced awkward mispronunciations of "OpenClaw", "SDK", and the version numbers that embarrassed the team in a dry run.

The DevRel engineer has asked you to prepare a production-ready bash script that uses the `sag` CLI tool to generate speech from this announcement text. The script needs to sound natural when played at the event, with appropriate pacing between major sections and expressive delivery for the exciting parts.

## Output Specification

Produce a single bash script named `announce.sh` that:
- Reads the announcement text aloud using `sag`
- Ensures correct pronunciation of any tricky terms
- Handles the numbers and URLs gracefully
- Adds appropriate pacing/breaks between sections
- Uses expressive delivery for the key moments

The script should be ready to run in an environment where `sag` is installed and configured with the appropriate API credentials.

## Input Files

The following file is provided as input. Extract it before beginning.

=============== FILE: inputs/announcement.txt ===============
Welcome to the OpenClaw SDK v2.5 launch.

Today we're excited to share that OpenClaw now supports 47 programming languages, delivers 99.9% uptime SLA guarantees, and processes requests 2.5x faster than the previous version.

Visit https://openclaw.dev/docs for the full API reference.

Our lead engineer, Dr. Anya Szymańska, will walk you through the new features.

OpenClaw SDK v2.5 — build smarter, ship faster.
