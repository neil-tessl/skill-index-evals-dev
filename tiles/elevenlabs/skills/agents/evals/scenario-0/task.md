# Voice-Powered Product Discovery Widget

## Problem/Feature Description

A mid-size e-commerce company called ShopVoice wants to add a voice AI assistant to their React storefront. When shoppers speak to the assistant, it should be able to highlight products visually in the page (by updating a product spotlight panel) and navigate the user to different sections of the site — all hands-free. The assistant should feel snappy and responsive with good error recovery so that network hiccups don't crash the page.

The frontend team has an existing React app and wants to integrate the ElevenLabs voice SDK. They need a self-contained React component that handles the full conversation lifecycle — starting/stopping the session, showing connection status to the user, and executing browser-side actions when the AI agent requests them. The team wants clean, idiomatic React code they can drop into their existing component tree.

## Output Specification

Produce a single file `voice-widget.tsx` (TypeScript React) that implements the `VoiceWidget` component described above. The component should:

- Accept an `agentId` prop (string)
- Display current connection status to the user
- Provide a button to start and stop the conversation
- Register two client tools that execute in the browser:
  - `highlight_product`: accepts `{ productId: string }`, updates `window.__spotlight = productId` and returns `{ success: true }`
  - `navigate_section`: accepts `{ section: string }`, updates `window.location.hash = section` and returns `{ success: true }`
- Handle errors from the conversation layer

Also produce a `package.json` listing the exact npm packages needed to run this component.
