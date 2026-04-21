# Automated Essay Scoring Pipeline

## Problem Description

EduBot is an AI tutoring platform that uses an LLM to give students feedback on their writing assignments. The team has been manually reviewing the LLM's essay feedback outputs weekly, but as the platform grows to thousands of students they can no longer keep up. They want to automate the quality-monitoring process using an LLM-as-judge approach.

The platform already has 200 historical essay feedbacks where human reviewers gave scores on several criteria. The team wants to use this labeled data to validate whether their automated judge agrees well enough with humans before they fully trust it. They also need to monitor quality over time once deployed.

The engineering team needs a Python module that implements their automated evaluation pipeline. The pipeline takes an essay feedback response, the original essay prompt, and a set of scoring criteria, then produces a quality score. The module should also include a section on how to measure whether the automated scores match their human-labeled historical data (the team will supply the comparison data separately).

## Output Specification

Produce the following files:

**`scoring_pipeline.py`** — A Python module implementing the direct scoring pipeline. It should:
- Accept a response (essay feedback), original prompt, and a list of criteria as inputs
- Validate the inputs before proceeding
- Load criteria from a JSON config file (not hardcoded)
- Build the LLM judge prompt (stub the actual API call — the important parts are the prompt construction and the output parsing logic)
- Return a structured result object/dict
- Include a sample run in a `if __name__ == "__main__"` block using the provided sample inputs below

**`criteria_config.json`** — The criteria configuration file loaded by the pipeline, with at least three criteria relevant to evaluating essay feedback quality

**`metrics_guide.md`** — A short document explaining which statistical metrics the team should use to validate their automated scores against the 200 human-labeled examples, and why — covering both the overall agreement question and per-criterion breakdown

## Input Files

The following sample data is provided for testing the pipeline. Extract it before beginning.

=============== FILE: inputs/sample_essay_prompt.txt ===============
Describe a challenge you faced and what you learned from it. (250-word essay prompt for high school students)

=============== FILE: inputs/sample_feedback.txt ===============
Your essay describes the challenge clearly and the conclusion shows genuine reflection. However, the middle section loses focus — the transition from describing the obstacle to explaining your response is abrupt. Consider adding a sentence that explicitly connects the two. The vocabulary is appropriate for the audience and there are no grammar errors. Overall, a solid piece that would benefit from stronger structural cohesion.
