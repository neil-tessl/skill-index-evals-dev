# Multi-Profile TTS Automation Setup

## Problem/Feature Description

A content production company is building an automated pipeline that uses `sag` to generate spoken-word audio across three very different production channels: a weekly podcast with rich emotional narration, a multilingual corporate training platform that serves audiences in English, German, and French, and a live customer-support chat widget that must respond with audio in under a second.

The engineering team needs a setup guide with ready-to-run bash scripts for each channel. The three channels have conflicting requirements — quality vs. speed vs. language coverage — and the team has been burned before by using the wrong settings for the wrong channel. They need clear separation between the three configurations and a way to lock in a default voice so all scripts are consistent.

## Output Specification

Produce a file named `tts-setup.sh` containing three bash functions or script sections — one per production channel — each configured appropriately for that channel's requirements. The file should also show how to set a persistent default voice.

Additionally, produce a `README.md` (max 30 lines) explaining which model was chosen for each channel and why.

The scripts should be ready to run in an environment where `sag` is installed and the appropriate environment variables are set.
