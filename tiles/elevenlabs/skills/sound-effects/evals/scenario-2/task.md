# Horror Game Sound Design: Atmospheric Audio Pack

## Problem/Feature Description

An indie horror game studio is creating a sound pack for their upcoming psychological horror title set in an abandoned asylum. The lead sound designer has a list of required audio moments — each with specific emotional and narrative intent — and needs a script that generates all of them in one run. The game requires a range of effects: some should be loosely interpreted by the AI to add unpredictable texture, while others need to closely follow the description to hit specific narrative beats (like a key sound that plays when a door unlocks).

The sound designer wants to iterate quickly by running the script repeatedly to audition different AI-generated variations. The script needs to produce all sounds as separate files so they can be dropped directly into the game engine's asset folder. The designer expects at least 5 distinct sound effects covering different moments in the game (ambient environment, creature sounds, UI/interaction sounds, and cinematic stings).

The API key will be available as an environment variable.

## Output Specification

Produce a Python or JavaScript script named `generate_horror_sfx` (with appropriate extension) that generates at least 5 sound effects and saves each to a separate audio file. The script should include inline comments explaining the intent behind each sound and why its settings were chosen.

Also produce a `sound_manifest.json` file that lists each generated filename and its corresponding description (what moment in the game it's for).
