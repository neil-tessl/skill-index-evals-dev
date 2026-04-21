# Customer Support Response Evaluator

## Problem Description

Contoso AI is building an automated quality assurance system for their customer support chatbot. They need to evaluate which of two candidate responses is better for a given customer query — for example, to select the best response when A/B testing new chatbot configurations.

The team has noticed that their initial comparison tool has a subtle problem: when they manually review evaluations, the first response in the comparison tends to win more often than it should, and longer responses seem to get an unfair advantage. This is producing skewed model selection decisions in production.

They need a Python module that compares two AI responses for a given prompt, using an LLM as the judge. The comparison must be robust to the ordering of responses and must not systematically favor verbosity. When the comparison produces inconsistent results, the evaluator should report that honestly rather than picking an arbitrary winner.

## Output Specification

Produce a single Python file `evaluator.py` that implements the pairwise comparison logic. The file should:

- Define a function (or class) that takes two responses and an original prompt as inputs
- Build the evaluation prompts used to call the judge LLM (the actual LLM calls can be stubbed or mocked — the important part is the prompt construction and the comparison logic)
- Demonstrate the full comparison protocol by running an end-to-end example with two sample responses and printing the result
- Return or print a final structured result (as JSON or a Python dict) for the sample comparison

The sample comparison should use these two responses to the prompt "Explain what recursion is in programming":

**Response A**: "Recursion is when a function calls itself. For example, to compute the factorial of n, you call factorial(n-1) until you reach the base case of factorial(0) = 1."

**Response B**: "Recursion in programming means a function invokes itself as part of its own definition. To prevent infinite loops, every recursive function needs a base case — a condition under which it stops calling itself. It is commonly used for tree traversal, divide-and-conquer algorithms, and problems that have a naturally recursive structure such as computing Fibonacci numbers."

Evaluation criteria for the sample: clarity, completeness, and accessibility for a beginner.

Save the output of running `python evaluator.py` to a file called `evaluator_output.txt` (or show it in a `if __name__ == "__main__"` block that produces clear output).
