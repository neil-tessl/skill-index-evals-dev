# Model Comparison Tool for Creative Writing

## Problem/Feature Description

A creative writing platform is running an A/B test between two versions of their story-generation model. Every week, the platform samples 200 pairs of story openings — one from each model variant — generated from the same user prompt. A head-to-head evaluation determines which model produces better results overall.

The previous evaluation setup used a single LLM pass to judge each pair, but the team noticed their results were suspiciously correlated with which response appeared first in the prompt. They suspect their evaluation method has a systematic flaw and want a more robust comparison system built from scratch.

The new system needs to compare pairs of responses and produce a winner determination with a calibrated confidence score. The team uses Claude to generate story openings and wants to make sure evaluation results are not biased by the model rating its own work highly.

## Output Specification

Produce a Python file `pairwise_evaluator.py` implementing the comparison module. The module should:
- Accept a prompt and two responses (response A and response B)
- Perform a fair comparison and return a winner (A, B, or TIE) with a confidence score
- Handle cases where the comparison produces an ambiguous result

Also produce `comparison_output.json` showing the result of running the evaluator on the provided sample pair.

## Input Files

The following sample is provided for testing your evaluator. Extract it before beginning.

=============== FILE: inputs/sample.json ===============
{
  "prompt": "Write the opening paragraph of a thriller novel set in a deep-sea research station.",
  "response_a": "The submersible touched down on the ocean floor with a metallic groan that Dr. Elena Vasquez felt in her teeth. Three miles of black water pressed against every porthole. The station's emergency beacon had gone silent six hours ago — and now, as her headlamp swept across the docking bay, she saw why. The airlock stood open.",
  "response_b": "Deep in the hadal zone, where pressure would crush an unprotected human body in milliseconds, the Poseidon Research Station had been home to twelve scientists for the past four months. Dr. James Okafor had reviewed their last transmission seventeen times. The words were calm, professional, routine — which was exactly what made them terrifying. Nobody spoke that calmly when everything was fine.",
  "criteria": ["narrative tension", "prose quality", "originality"],
  "generator_model": "claude-sonnet-4-5"
}
