# Meeting Records Automation for a Legal Practice

## Problem/Feature Description

A boutique litigation firm currently has paralegals manually transcribing client consultation recordings. Each month this consumes over 40 hours of billable paralegal time. The transcripts are critical for case preparation: attorneys need to quickly review what each party said, so the final output must clearly attribute statements to individual speakers. Mixing up who said what can have serious consequences in litigation contexts.

The firm wants to integrate speech-to-text transcription into their nightly case management pipeline. Recordings are uploaded to a shared drive each evening, and an automated job should process them overnight. Because it runs unattended as part of a larger pipeline, the transcription step must not produce any interactive output — only the transcript content should reach downstream systems. The output format needs to be machine-readable so the case management software can parse and index the content for search and review.

## Output Specification

Write a shell script named `process_meeting.sh` that:
- Accepts a path to an audio recording file as its first argument
- Produces a transcript to stdout or writes it to a file alongside the input
- Is designed to run without human supervision as part of an automated batch job

Also write a short `README.md` explaining the prerequisites and how to invoke the script.
