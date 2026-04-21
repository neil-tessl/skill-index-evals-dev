# Customer Support Voice Agent for RetailCo

## Problem/Feature Description

RetailCo's customer service team handles hundreds of calls per day for order lookups and escalations to human agents. They want to automate first-line support with a voice AI agent that can look up order status via their internal API and escalate to a human when needed. The agent must be reliable and have a warm, professional tone.

You are a backend engineer tasked with writing the Python script that creates this agent programmatically on the ElevenLabs platform. The agent must integrate with two external systems: a webhook endpoint for order lookups (`https://api.retailco.internal/orders/lookup`), and a built-in call transfer capability that can forward callers to a human support line.

The order lookup endpoint requires an `Authorization` header. Since this agent will be deployed to both staging and production environments, the API host and secret should be resolved from workspace environment variables rather than hardcoded — so the same agent configuration works across deployments.

The ops team cares about reliability: the order lookup sometimes takes up to 25 seconds under load, and they want the agent configuration to reflect this explicitly.

## Output Specification

Produce a Python script `create_agent.py` that:

1. Creates the RetailCo support agent on ElevenLabs using the Python SDK
2. Configures an order lookup webhook tool with appropriate description, correct HTTP method, timeout, and environment-variable-based URL and auth header
3. Configures an end-call system tool and a phone transfer system tool pointing to `+15551234567` (transfer when user asks for human support)
4. Uses a voice optimized for low latency with the fastest recommended TTS model
5. Sets an appropriate first message and system prompt

The script should print the created agent's ID on success.
