# Voice Character Reply Scripts for Chat Assistant

## Problem/Feature Description

A developer is building a chat assistant called "Clawd" that can respond to users with audio messages in different personality styles. Users can request replies in one of three moods: an enthusiastic scientist who gets very animated when explaining things, a calm and reassuring advisor for sensitive topics, or a dramatic storyteller for entertainment content.

The developer needs bash scripts that generate the appropriate audio reply for each character type when a user triggers a voice response. The scripts will be called by the chat backend, which picks up the audio file from a fixed location and embeds it in the chat UI. The character voices need to feel genuinely different — just changing the voice model isn't enough; the delivery itself must reflect the personality.

## Output Specification

Produce a file named `voice-replies.sh` containing three bash functions:
- `scientist_reply <message>` — generates an enthusiastic scientist response
- `calm_reply <message>` — generates a calm, soothing response  
- `dramatic_reply <message>` — generates a dramatic storyteller response

Each function should generate the audio file and then output the correct line that the chat backend needs to embed the audio in the reply.

Include a short `voice-replies-demo.sh` that calls each function with a sample message to demonstrate the three styles.
