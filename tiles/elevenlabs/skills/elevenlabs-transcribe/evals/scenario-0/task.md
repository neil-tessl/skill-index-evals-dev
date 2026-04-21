# Meeting Transcription Pipeline

## Problem/Feature Description

Your organization records all-hands meetings, team standups, and client calls as audio files and stores them in a shared directory. The legal and compliance team now needs these recordings indexed as structured data — specifically, they want a machine-readable transcript with timestamps and labeled speaker turns for every recording. The HR team also wants to run keyword searches across the transcripts to find action items.

The recordings directory has accumulated dozens of MP3 and WAV files from the past quarter. You have been asked to write an automation script that a DevOps engineer can run on any batch of recordings. The script should be self-contained, easy to re-run, and must produce one structured output file per audio input.

## Output Specification

Write a shell script named `process_meetings.sh` that:
- Accepts a directory path as its argument
- Iterates over all `.mp3` and `.wav` files in that directory
- Transcribes each file and saves the output as a `.json` file alongside the original (e.g., `meeting.mp3` → `meeting.json`)
- Prints a summary to stdout when done showing how many files were processed

The script should work non-interactively without any human prompting during execution.

Also create a brief `README.md` explaining how to set up and run the pipeline, including any environment prerequisites.

## Input Files

The following sample manifest is provided to help you test the script's directory-iteration logic. Extract the file before beginning.

=============== FILE: inputs/recordings/sample_meeting.txt ===============
This is a placeholder representing meeting recordings in this directory.
Real files would be: q1_all_hands.mp3, team_standup_2024-03-01.wav, client_call_acme.mp3
