# Background Music Generator for Podcast Platform

## Problem/Feature Description

A podcast hosting platform is adding an AI music feature so that creators can generate custom intro and outro tracks without hiring composers. The team wants a Node.js script that producers can run from the command line. The script should take a short text description of the vibe they want and produce a 45-second MP3 ready to drop into their editing software.

The engineering lead has asked for a clean TypeScript or JavaScript solution using the ElevenLabs music capabilities. The platform already manages API credentials through environment variables, so the script must pick up the key from the environment rather than accepting it as a CLI argument. The lead is particular about keeping dependencies minimal and using only officially supported packages.

## Output Specification

Write a Node.js script (JavaScript or TypeScript) named `generate-podcast-music.js` (or `.ts`) that:

- Accepts a music description as a command-line argument (e.g. `node generate-podcast-music.js "upbeat indie folk with acoustic guitar"`)
- Generates a 45-second music track
- Saves the output as `podcast-intro.mp3` in the current directory
- Prints a short status message when the file is saved

Also produce a `package.json` listing the dependencies needed to run the script.
