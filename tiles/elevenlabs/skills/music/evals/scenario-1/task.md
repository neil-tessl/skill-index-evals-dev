# Custom Orchestral Score Generator with Section Control

## Problem/Feature Description

A game studio is producing a cinematic trailer for their new title and needs a 60-second orchestral track with a specific narrative arc: a quiet, tense opening that builds into a triumphant climax. Their audio director has rejected previous AI-generated tracks because the structure was too uniform — they need to be able to inspect the generated musical structure before committing to audio rendering, and potentially adjust the pacing of individual sections.

Write a Python script that gives the audio director fine-grained control over the music structure. The script should first produce an intermediate structural description of the track so the director can review it (print it to stdout), and then generate the final audio from that structure. The audio director also wants to see which global musical styles the system chose, so those should be printed as well.

## Output Specification

Write a Python script named `generate-trailer-score.py` that:

- Generates a 60-second orchestral music track suited for a cinematic game trailer
- Prints the global positive styles chosen for the composition
- Prints each section name and its duration
- Saves the final audio as `trailer-score.mp3`

Also include a `requirements.txt` listing the Python packages needed to run the script.

The script must be runnable with just `ELEVENLABS_API_KEY` set in the environment — no other configuration or input files should be required.
