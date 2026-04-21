# Multilingual Podcast Archive Transcription Pipeline

## Problem/Feature Description

A podcast distribution platform hosts content from independent creators across Latin America, France, and Portugal. They have an archive of several thousand episodes recorded in Spanish, French, and Portuguese that need to be transcribed and made searchable. Their product team has noticed that transcription quality is noticeably worse when the language isn't specified upfront, particularly for Portuguese content where auto-detection sometimes defaults to Spanish.

Beyond spoken words, the platform also wants to enrich their transcripts with structural markers. Many episodes feature musical intro and outro segments, audience laughter on panel shows, and applause on live recordings. These moments are valuable for generating chapter markers and show notes automatically — a feature their creators have been requesting for months.

The archive is organized into language-specific subdirectories (`es/`, `fr/`, `pt/`) under a root directory. An overnight batch job needs to process the entire archive, running quietly without cluttering log files with setup messages.

## Output Specification

Write a shell script named `transcribe_archive.sh` that:
- Accepts the root archive directory as its first argument
- Iterates over the language subdirectories (`es/`, `fr/`, `pt/`) and processes `.mp3` files within each
- Writes transcripts to a `transcripts/` subdirectory that mirrors the language structure

Include comments in the script that explain the key options being used and why. You can assume the `transcribe.sh` script is available at a path stored in a `TRANSCRIBE_SH` variable that the caller will set, or use `./transcribe.sh` as a default.
