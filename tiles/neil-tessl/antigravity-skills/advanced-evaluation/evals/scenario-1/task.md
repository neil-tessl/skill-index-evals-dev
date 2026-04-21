# Legal Document Review Evaluation Rubric

## Problem Description

LexAI is deploying an LLM-based assistant that reviews legal contracts for a law firm. Before going live, the team needs to establish a consistent quality standard for evaluating the assistant's contract analysis outputs. Individual lawyers on the team have been scoring the assistant's outputs manually, but scores vary widely — one reviewer rates the same output a 3 while another gives it a 5, making it impossible to track quality improvements over time.

The team wants to create formal evaluation rubrics so that any reviewer (human or automated) produces consistent, reproducible scores. They plan to use these rubrics both for human spot-checks and to train an automated LLM judge. The rubrics need to be rigorous enough for a professional legal context, where imprecision or missing nuance could have real consequences for clients.

Specifically, they need rubrics for the following two criteria that matter most when reviewing legal contract analyses:

1. **Legal Accuracy** — Whether the assistant's legal claims, interpretations, and conclusions are factually and legally correct
2. **Clarity of Explanation** — Whether the assistant's analysis is comprehensible to a non-lawyer client who needs to make a business decision based on the review

## Output Specification

Generate two rubric files:
- `rubric_legal_accuracy.json` — rubric for Legal Accuracy
- `rubric_clarity.json` — rubric for Clarity of Explanation

Each rubric file should be a structured JSON document. Also produce a short `rubric_summary.md` explaining the key design decisions you made and why they are appropriate for this use case.

The rubrics will be used in production for a high-stakes legal setting where errors have serious client consequences — factor this into your design choices.
