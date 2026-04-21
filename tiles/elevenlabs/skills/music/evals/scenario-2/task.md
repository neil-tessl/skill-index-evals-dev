# Music Library Generator with Metadata Archive

## Problem/Feature Description

A podcast production studio is building an internal music library tool. They need a Python script that generates background music tracks for various podcast formats — interview intros, transition stings, and closing themes — and stores not just the audio but also structured metadata about each generated track. The metadata will feed into an internal catalog system where producers can search tracks by their musical characteristics, section breakdowns, and styles.

Additionally, the studio has strict licensing policies: all music used must be instrumental (no vocals allowed), and the team had a previous incident where a developer accidentally generated music by referencing a famous artist's name in a prompt, which caused an API rejection. The new tool needs to handle such errors gracefully and continue processing.

Write a Python script `generate_library.py` that:

1. Generates three podcast music tracks: an interview intro, a transition sting, and a closing theme.
2. For each track, retrieves both the audio AND the structured composition metadata (plan + any song metadata) in a single API call.
3. Saves each audio file using the filename provided by the API response.
4. Saves the composition metadata for each track as `{track_name}_metadata.json`.
5. Implements error handling that catches API errors and, when the error response includes a suggested alternative prompt, logs that suggestion to a file `error_suggestions.txt` and retries with the suggested prompt.
6. Ensures all generated tracks are purely instrumental.

Also write a `library_summary.md` explaining which API method was used and why (one paragraph), and noting any error-recovery logic implemented.

Since real API calls require credentials, write the script with the API calls commented out but structurally complete and syntactically valid.
