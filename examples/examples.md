# Examples

Sample outputs are illustrative. Real answers will vary.

## 1. Answer mode (default)

**Input:** `/refine explain recursion`

**Refined prompt**
> Explain recursion to a first-year computer science student: what it is, the base case and the recursive case, a simple factorial example in Python with comments, how the call stack behaves, and one common mistake. Keep it clear and practical.

*Assumptions:* Python is the example language; beginner level.

Then the skill gives the full explanation.

## 2. Portable mode

**Input:** `refine for any AI: summarize a research paper`

```
Task: Summarize the research paper provided below for a non-specialist reader.
Context: I want to decide whether the paper is worth reading in full.
Audience and level: Educated reader, no background in the field.
Inputs: [PASTE PAPER TEXT OR ABSTRACT HERE]
Constraints: Use only the provided text. If something is unclear or missing, say so instead of guessing.
Output format: 1) One-sentence takeaway. 2) Key question, method, and findings in 3 to 5 bullets. 3) Limitations. 4) Whether it is worth a full read, and why.
Quality bar: Accurate, plain language, under 250 words.
```
**What changed:** added audience, a strict grounding rule, and a fixed output structure.
**Fill in before use:** `[PASTE PAPER TEXT OR ABSTRACT HERE]`

## 3. Tuned mode

**Input:** `give me a version for ChatGPT and Gemini: plan a study schedule`

The skill returns the portable prompt first, then a short variant for each named model with one line on what was adjusted and why, and a note that model behavior changes over time.

## 4. Critique mode

**Input:** `critique this prompt: Write me a good essay about climate`

The skill returns a score out of 10 for clarity, context, constraints, and output format, the top 3 fixes (topic angle, audience and length, thesis and structure), and an improved version in a code block.

## 5. Already-good prompt

**Input:** `/refine Write a Python function that merges two sorted lists in O(n) time, with a docstring and 3 pytest tests.`

The skill notes in one line that the prompt is already clear and detailed, then answers it directly.
