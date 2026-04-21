# Global Podcast Archive Transcription

## Problem/Feature Description

A media company distributes podcasts in six languages across markets in North America, Latin America, and Europe. They have an archive of several hundred episode audio files, each already tagged with its language in a metadata manifest. The editorial team wants full-text search across the archive and also wants to annotate episodes that contain background music intros and audience laughter for their UX team, who will use those markers in a redesigned player.

You have been asked to write a Python script that reads the manifest, transcribes each episode, and writes the results to an output directory. The editorial team specifically wants to see non-speech audio events captured in the output, not just spoken words. Accuracy is important, so the language information from the manifest must be passed to the transcription service — relying on auto-detection alone has caused too many errors in Portuguese and French episodes.

## Output Specification

Write a Python script named `transcribe_archive.py` that:
- Reads `inputs/manifest.json` (provided below)
- For each episode, calls the transcription service with the correct language hint and audio event tagging enabled
- Writes each transcript to `outputs/<episode_id>.txt` (plain text) and `outputs/<episode_id>_events.json` (JSON with event annotations)
- Prints progress to stdout as it processes each file

Also write a short `run_instructions.txt` explaining what environment variables and tools must be set up before running the script.

## Input Files

The following manifest is provided. Extract it before beginning.

=============== FILE: inputs/manifest.json ===============
{
  "episodes": [
    {"id": "ep001", "file": "recordings/ep001_english_interview.mp3", "language": "en", "title": "Tech Roundup"},
    {"id": "ep002", "file": "recordings/ep002_portuguese_talk.mp3", "language": "pt", "title": "Papo Tech"},
    {"id": "ep003", "file": "recordings/ep003_french_news.wav", "language": "fr", "title": "Les Nouvelles"},
    {"id": "ep004", "file": "recordings/ep004_spanish_comedy.mp3", "language": "es", "title": "Comedia"},
    {"id": "ep005", "file": "recordings/ep005_german_lecture.wav", "language": "de", "title": "Vortrag"},
    {"id": "ep006", "file": "recordings/ep006_italian_music.mp3", "language": "it", "title": "Musica"}
  ]
}
