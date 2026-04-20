# AI Tutor Response Evaluator

## Problem/Feature Description

An ed-tech startup has deployed an AI tutoring assistant to help middle and high school students understand STEM concepts. The product team needs to automate quality assurance: right now human reviewers spot-check a sample of tutor responses each week, but with hundreds of thousands of daily interactions this approach misses most quality issues.

The team wants a Python evaluation module that uses an LLM as judge to score tutor responses against defined quality criteria. They have agreed on three criteria they care about: whether the explanation is scientifically accurate, whether the language is appropriate for the target age group, and whether the response is engaging enough to keep students motivated. Each criterion has a different importance weight that the team has already decided on.

The evaluation module needs to produce structured, auditable results so that quality reviewers can understand why a response received a particular score — not just the final number. The team plans to use these scores to flag low-quality responses for human review and to track quality trends over time.

## Output Specification

Produce a Python file `evaluator.py` implementing the evaluation module. The module should:
- Accept a student prompt, a tutor response, and a list of criteria (each with a name, description, and weight)
- Call an LLM to score the response and return structured results
- Include a working example that demonstrates scoring the provided sample

Also produce `evaluation_output.json` containing the result of running the evaluator on the sample input below.

## Input Files

The following sample is provided for testing your evaluator. Extract it before beginning.

=============== FILE: inputs/sample.json ===============
{
  "prompt": "Why does the Moon always show the same face to Earth?",
  "response": "The Moon always shows us the same face because of something called tidal locking. Gravity from Earth has slowly slowed down the Moon's spin over billions of years until the time it takes to rotate once exactly matches the time it takes to orbit Earth — about 27 days. So even though the Moon is rotating, it rotates at the same rate it orbits, which means the same side always faces us. It's like if you walked in a circle around a friend while slowly spinning so that you always faced them.",
  "criteria": [
    {"name": "Scientific Accuracy", "description": "Correctness of the scientific explanation and mechanisms described", "weight": 5},
    {"name": "Age-Appropriate Language", "description": "Language and analogies suitable for middle or high school students", "weight": 3},
    {"name": "Engagement", "description": "Response is interesting and motivates continued learning", "weight": 2}
  ]
}
