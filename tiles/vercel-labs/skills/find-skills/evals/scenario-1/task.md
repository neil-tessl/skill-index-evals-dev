# Automating Agent Skill Setup for a New Developer Machine

## Problem/Feature Description

Your company onboards new developers frequently, and the DevOps team wants to automate part of the setup process for AI-assisted development environments. One step is ensuring every developer's agent has a skill installed for Docker and Kubernetes workflow assistance — a common need across the engineering team given their containerized deployment pipeline.

You've been asked to research available skills for container/Kubernetes workflows and produce a setup script that the onboarding automation can run. The script needs to work non-interactively (no prompts) and install the skill at the user level so it's available globally across all projects.

## Output Specification

Produce two files:

1. `install.sh` — A shell script containing the exact command(s) to install the best skill you found. The script should be runnable without any user interaction.
2. `discovery_notes.md` — A brief document explaining how you found the skill, what sources you checked, and why you chose this particular skill over alternatives.

Clean up any large downloaded files before finishing.
