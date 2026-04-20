# Clinical Documentation Evaluation Framework

## Problem/Feature Description

A digital health company has built an AI assistant that helps physicians draft clinical notes from audio recordings of patient encounters. Before deploying to hospitals, the company must validate that the assistant's output meets clinical documentation standards. Their regulatory team requires a formal validation study comparing AI-generated notes to those written by experienced physicians.

The quality team needs two things: first, a structured scoring rubric that physicians can use to evaluate AI-generated clinical notes on the criterion of Clinical Information Completeness (whether all medically relevant information from the encounter is captured); second, a plan for which statistical metrics to use when analyzing the validation study results and comparing automated evaluation to physician ground truth.

The rubric will be used by hospitalists with busy schedules, so it needs to be precise and leave as little room for interpretation as possible. The domain is internal medicine clinical documentation. Given that patient safety is at stake, the evaluation standards should reflect that context.

## Output Specification

Produce two output files:

1. `rubric.json` — a structured scoring rubric for the "Clinical Information Completeness" criterion. The rubric should cover all score levels and provide everything an evaluator needs to apply it consistently.

2. `metrics_plan.md` — a markdown document explaining which statistical metrics should be used to:
   - Measure agreement between physician reviewers (inter-rater reliability)
   - Validate the automated evaluation scores against physician ground truth
   - Detect and report any systematic patterns in disagreements
