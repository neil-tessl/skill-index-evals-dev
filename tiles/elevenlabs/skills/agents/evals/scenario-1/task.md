# Customer Support Voice Agent with CRM Integration

## Problem/Feature Description

RetailFlow, an e-commerce platform, wants to add a voice-based customer support agent that can look up order status in real time during a phone call. The company runs two environments — staging and production — with different CRM API base URLs and different API key secrets. They want a single agent configuration that works in both environments without storing any credentials directly in the config files.

The agent should be able to look up an order when a customer provides their order ID, and escalate to a human support line if the issue is too complex. The team needs the full agent configuration written as a Python script that creates the agent with both the CRM lookup capability and the escalation mechanism wired up. The script should work regardless of which environment it is deployed in, as long as the workspace environment variables are set correctly for that environment.

## Output Specification

Produce the following files:

- `create_agent.py` — Python script that creates the ElevenLabs agent with a full `conversation_config` including the CRM webhook tool, an escalation built-in tool, and TTS settings optimized for low latency. The webhook tool should call a CRM order lookup endpoint that varies by environment, and should use a secret API key from the workspace rather than a hardcoded value.
- `README.md` — Brief explanation of which workspace environment variable labels need to be set and what values they expect (CRM host and API key).

The CRM webhook URL pattern should incorporate the environment-specific base host. The API key should be passed as an Authorization header. Include a human escalation path for when customers can't be helped by the AI alone.
