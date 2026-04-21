# Voice-Enabled Product Demo Assistant

## Problem/Feature Description

A B2B SaaS company called Lumino is adding a voice AI assistant to their product demo page. When prospective customers visit the demo page, they can have a live voice conversation with an AI that walks them through the product's key features. The team wants the assistant to dynamically reveal different product screenshots or highlight UI elements as it mentions each feature — so the agent needs to trigger browser-side UI updates during the conversation.

The engineering team has set up the ElevenLabs agent on the backend (Python) and now needs the React frontend component to be built. They want it to handle errors gracefully in one place and to use a modern, maintainable patterns rather than grabbing a single monolithic hook that does everything. The component should show a "Start conversation" button when idle and allow the user to end the session once connected. It must also respond to the agent calling a `highlight_feature` tool, which should cause the corresponding feature card on the page to visually highlight.

## Output Specification

Produce the following files:

- `agent_setup.py` — Python script that creates the ElevenLabs agent with the `highlight_feature` client tool registered in its configuration. The agent's system prompt should mention it can highlight product features.
- `ConversationWidget.tsx` — React TypeScript component that starts/ends sessions, handles errors, and registers the `highlight_feature` client tool handler.
- `package.json` — listing all required npm dependencies.

The `highlight_feature` tool should accept a `feature_id` parameter (string) and the browser-side handler should log or manipulate a DOM element with id equal to `feature_id`.
