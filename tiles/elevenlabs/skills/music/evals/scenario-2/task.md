# Resilient Music Generation CLI with Prompt Retry

## Problem/Feature Description

A content agency uses AI-generated music for social media videos. Their copywriters sometimes describe music in terms of well-known artists or song titles, which causes the generation API to reject the request. The agency wants a Python CLI tool that handles these rejections gracefully: when a prompt is flagged, the tool should automatically retry using the alternative phrasing that the API itself suggests, rather than failing with an unhelpful error message.

The tool also needs to support scoring background music to existing video clips. Videos are provided as local file paths, and the music should match the mood described by the user. Style guidance should be split sensibly: the overall musical narrative goes in the description, while short mood or genre keywords go as separate style tags.

The engineering team wants a single script that handles both use-cases (prompt-based generation and video scoring) and recovers automatically from content policy rejections in both flows.

## Output Specification

Write a Python script named `music_cli.py` that supports two sub-commands:

1. `python music_cli.py generate "<prompt>" <output_file.mp3>` — generates music from a text prompt and saves to the given output filename. Duration should default to 30 seconds.
2. `python music_cli.py score "<description>" "<tag1,tag2,...>" <video_file> <output_file.mp3>` — generates background music for a single video file

For both sub-commands:
- If the API rejects the request due to a content policy violation (e.g. referencing a specific artist), the script must automatically retry once using the alternative phrasing provided by the API error response
- Print a short message indicating whether a retry was needed

Also include a `requirements.txt` file listing all required Python packages.

The script must work with only `ELEVENLABS_API_KEY` set in the environment.
