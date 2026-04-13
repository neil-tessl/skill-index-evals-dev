# Sound Effects Generator for a Game Studio

## Problem Description

A small indie game studio is building a Node.js tool that lets their sound designers quickly prototype audio assets. The designers type a description, and the tool fetches a generated sound effect from ElevenLabs and saves it as an MP3 file — ready for drop-in testing inside the game engine.

The existing team members have mostly worked with the ElevenLabs text-to-speech API before, so they want the new tool to follow the same general pattern: a small self-contained Node.js script that reads the API key from the environment and saves the result to disk.

## Output Specification

Write a Node.js script `generate-sfx.js` that:
- Accepts a sound description as a command-line argument (e.g. `node generate-sfx.js "Heavy wooden door creaking open"`)
- Calls the ElevenLabs sound effects API with that description
- Saves the resulting audio to `output.mp3` in the current directory
- Prints a short message to the console when it succeeds or if it encounters an error

Also include a `package.json` (or show the install command in a comment) so that the required dependencies are clear.
