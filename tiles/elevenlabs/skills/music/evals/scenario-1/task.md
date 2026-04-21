# Automated Video Score Generator for a Documentary Series

## Problem/Feature Description

A production company is post-producing a 4-part nature documentary series. Each episode has multiple scenes that need original background music synchronized to the footage. The editor wants a Python script that takes a set of video clips and automatically generates fitting background scores for each scene.

The team has three short video clips from different episodes: a tranquil ocean sunset, a fast-paced wildlife chase, and a mysterious cave exploration sequence. Each needs a distinct musical treatment. The clips vary in length and mood, and the team wants to steer both the narrative arc of the music (using a longer description) and quickly communicate the sonic palette (using brief style labels separately from the description).

Write a Python script `generate_scores.py` that generates background music for each of the three provided video clips using the appropriate ElevenLabs API endpoint. For each clip, the script should:
- Use the video file as input to the music generation
- Provide a high-level narrative description of what the music should accomplish emotionally
- Provide concise style keywords separately from the description
- Save the resulting audio as `score-{clip_name}.mp3`

Also write a `generation_plan.md` that documents, for each clip:
- The API method used
- The description provided
- The style keywords provided (listed separately from the description)
- How many style keywords were used
- The output filename

Since real API calls require credentials, write the script with the API calls commented out but structurally complete. The script should be syntactically valid Python.

## Input Files

The following files are provided as inputs. Extract them before beginning.

=============== FILE: inputs/clips_manifest.json ===============
{
  "clips": [
    {
      "filename": "ocean_sunset.mp4",
      "duration_seconds": 45,
      "scene": "A slow pan across a golden ocean horizon at dusk, pelicans gliding",
      "mood": "peaceful, reflective, warm"
    },
    {
      "filename": "wildlife_chase.mp4",
      "duration_seconds": 28,
      "scene": "A cheetah sprinting across savannah grass in pursuit of a gazelle",
      "mood": "urgent, exciting, primal"
    },
    {
      "filename": "cave_exploration.mp4",
      "duration_seconds": 52,
      "scene": "Spelunkers with headlamps descend into an unexplored cavern system",
      "mood": "mysterious, tense, wonder"
    }
  ]
}
