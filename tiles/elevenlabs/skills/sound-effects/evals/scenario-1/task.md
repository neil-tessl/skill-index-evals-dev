# Looping Ambient Soundscape Generator

## Problem Description

A meditation app startup needs a Python utility that generates seamlessly looping background audio for their in-app relaxation scenes. Each scene has a theme (e.g. rainforest at dawn, crackling fireplace, ocean waves at night) and needs a short audio clip that loops without audible seams — so users can leave a scene running for as long as they like without noticing a restart.

The audio team doesn't want to manually stitch recordings; they want a script that generates a polished looping ambient clip on demand, given a scene description. The clips should be around 10–15 seconds long so they are short enough to loop quickly but long enough that the loop point isn't jarring. The team values creative, detailed prompts because early tests showed that vague descriptions produced underwhelming results.

## Output Specification

Write a Python script `generate_loop.py` that:
- Accepts a scene description as a command-line argument (e.g. `python generate_loop.py "Rainforest at dawn with distant bird calls"`)
- Generates a looping sound clip and saves it to `ambient_loop.mp3`
- Prints a confirmation message on success, or an error message if something goes wrong

The script should be runnable with the ElevenLabs API key available in the shell environment.
