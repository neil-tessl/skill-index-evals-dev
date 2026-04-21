# Unified News Media Transcription Router

## Problem/Feature Description

A media intelligence company provides transcription services to newsrooms and press monitoring agencies. Their clients submit two distinct types of transcription jobs through the same API: archived broadcast recordings from the previous day (stored as local audio files) and live broadcast streams that are currently on air (identified by streaming URLs).

Currently the company has separate ad-hoc scripts for each case, maintained by different team members, which has led to inconsistency and operational confusion. The engineering lead wants a single unified command-line tool that intelligently routes to the correct transcription approach based on whether the input is a local file or a stream URL. The tool feeds into a monitoring dashboard, so all transcription output must be clean — no setup or status chatter in the output stream.

The ops team has also asked whether there's a way to replay archived recordings as if they were live, to test the real-time pipeline components using known content before a major broadcast event.

## Output Specification

Write a shell script named `news_transcribe.sh` that:
- Accepts a single input argument: either a local audio file path or a streaming URL
- Automatically detects the type of input and uses the appropriate transcription approach
- Writes transcribed output to a file named `transcript.txt` in the current directory

Also write a `USAGE.md` documenting the two modes with example invocations for both a local file and a streaming URL. You can assume transcribe.sh is available at a path stored in a `TRANSCRIBE_SH` environment variable, defaulting to `./transcribe.sh`.
