# Multi-Format Sound Asset Pipeline

## Problem Description

A podcast hosting platform is building a content-enrichment feature that auto-generates short audio stings and transitions for episodes. Their infrastructure team wants a simple Bash script that the CI pipeline can call to produce audio assets in two different formats: one in the highest-fidelity format available for the web player, and another in a format compatible with telephony systems (for users who dial in to listen).

The team's existing tools all use plain curl — no SDKs or runtimes are available in the CI Docker image. They need a single self-contained shell script that takes a sound description, calls the ElevenLabs API twice (once per format), and saves each result to a separate file. The pipeline operator will set credentials as environment variables before running the script.

## Output Specification

Write a Bash script `generate_assets.sh` that:
- Accepts a sound description as the first argument (e.g. `bash generate_assets.sh "Upbeat tech startup intro sting with a digital chime"`)
- Calls the ElevenLabs sound-generation API twice:
  1. Once to produce a high-fidelity audio file saved as `asset_hq.mp3` (or appropriate extension)
  2. Once to produce a telephony-compatible audio file saved as `asset_phone.wav` (or appropriate extension for that format)
- Prints the file sizes of both output files on success
- Exits with a non-zero code if either API call fails

The script must work without any additional dependencies beyond curl and standard shell utilities.
