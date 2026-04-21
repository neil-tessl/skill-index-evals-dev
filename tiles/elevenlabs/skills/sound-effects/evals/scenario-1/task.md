# Post-Production Sound Pipeline: Batch Audio Generator

## Problem/Feature Description

A documentary production company is building an automated post-production pipeline in Python. Their audio supervisor needs a batch script that generates multiple sound effects for different delivery targets from the same session. The challenge is that the same sound may need to be delivered in different formats: a high-quality uncompressed version for the final archive, a compressed version for streaming previews, and a telephony-quality version for automated phone menus that use some of the documentary's audio branding.

The audio supervisor also wants fine-grained control over how closely the output matches each description — some effects should be loosely interpreted for creative results, while others need to precisely match the brief. Duration matters too: some effects need to be exactly timed to hit specific edit points.

The API key will be available as an environment variable. The script should be runnable directly and save all generated files to the current directory.

## Output Specification

Produce a Python script named `generate_sfx.py` that generates at least three sound effects, each demonstrating different combinations of audio format, duration, and prompt adherence settings. Save the outputs as audio files. Include comments in the script that explain the format choices for each sound effect.

Also produce a `requirements.txt` listing the Python dependencies needed.
