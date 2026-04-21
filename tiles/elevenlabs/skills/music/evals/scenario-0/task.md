# Adaptive Soundtrack Generator for Indie Game

## Problem/Feature Description

A small indie game studio is building a procedurally generated dungeon crawler and wants dynamic background music that matches each zone's atmosphere. The game has four distinct zones — a haunted forest, an underground lava cavern, a celestial sky temple, and a final boss arena — and the team wants distinct tracks for each. Rather than licensing music, they want AI-generated tracks that fit the mood precisely.

The lead developer has been experimenting with AI music generation and wants a TypeScript script that generates all four tracks. Crucially, the team wants fine-grained control: they want to inspect and potentially modify the musical structure (styles, sections) before committing to audio generation, so that they can iterate on the feel of each zone without regenerating from scratch every time.

## Output Specification

Write a TypeScript script `generate_music.ts` that:

1. For each of the four game zones, generates a composition plan from a descriptive prompt and logs the plan's positive global styles to the console.
2. Uses the composition plan (not the raw prompt) to generate the final audio for each zone.
3. Saves each audio track as `zone-{n}.mp3` (e.g., `zone-1.mp3` through `zone-4.mp3`).
4. Each track should be approximately 30 seconds long.

Also produce a `process_log.md` file documenting:
- Which npm package(s) were installed
- The import statement used for the ElevenLabs client
- For each zone: the prompt used, a summary of the composition plan's global styles, and the output filename

Do not generate the actual audio files (the API call will fail without a real key) — instead, write the script and log as if the process were being documented for a teammate who will run it with real credentials. Comment out the actual API calls so the script is syntactically valid but won't execute network requests.
