# Live Broadcast Monitoring Tool

## Problem/Feature Description

A news monitoring startup tracks radio and podcast streams for keyword mentions on behalf of PR clients. Their current setup manually downloads and batches recordings, which introduces a 30-minute lag before transcripts are available. The engineering team wants to switch to real-time transcription so alerts can be fired within seconds of a keyword being spoken.

The tool needs to connect to a live audio stream URL, transcribe the audio as it arrives, and print each committed transcript segment to stdout so a downstream process can pipe it into a keyword detection engine. The PR team has also requested a "monitoring mode" where a human operator watches the terminal and sees words appearing almost instantly as they're spoken — so low-latency partial results should be available as a flag rather than the default behavior.

You have been asked to write a shell script named `monitor_stream.sh` that wraps the transcription tool for this use case. The script should accept a stream URL as its first argument and an optional `--show-partials` flag for the monitoring mode. Write the script and a `design_notes.md` explaining the approach and the flags used.

## Output Specification

- `monitor_stream.sh` — a shell script that accepts `<url>` and optional `--show-partials`
- `design_notes.md` — explains the design choices and which flags enable each feature (no more than one page)
