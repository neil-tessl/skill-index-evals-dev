# Game Audio Module: Procedural Sound Effects

## Problem/Feature Description

A small indie game studio is building a Node.js-based game engine and needs a module that generates procedural sound effects at runtime using AI. The audio team currently hand-crafts all sounds in a DAW, which creates a bottleneck every time a designer wants to test a new effect. They want a reusable JavaScript module that can generate three categories of sounds on demand: an ambient background loop for the main dungeon level, a short UI chime that plays when a player picks up an item, and a heavy impact sound for when a boss hits the player.

The API key will be available as an environment variable at runtime. The module should handle the audio output gracefully and write each generated sound to its own file so the game engine can load them as assets.

## Output Specification

Produce a self-contained JavaScript file named `generate-sounds.js` that:
- Generates the three sounds described above and writes them to `dungeon-ambient.mp3`, `pickup-chime.mp3`, and `boss-impact.mp3`
- Includes a `package.json` (or inline install instructions) showing how to install the required dependency
- The ambient background sound should loop seamlessly

Also produce a brief `README.md` describing how to run the script and what environment variable is needed.
