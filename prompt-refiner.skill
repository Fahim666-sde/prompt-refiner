---
name: prompt-refiner
description: Turns a rough, short, or vague prompt into a clear, detailed, well-structured prompt that works on any AI model (Claude, ChatGPT, Gemini, Llama, Mistral, DeepSeek, Qwen, Perplexity, coding agents, image or video generators), then either answers it or hands it back ready to paste. Supports four modes - Answer (refine then answer, the default), Portable (model-agnostic prompt only), Tuned (variants for named models), and Critique (score and improve a prompt the user already wrote). Use whenever the user says "refine", "/refine", "improve my prompt", "make this prompt better", "polish this prompt", "fix my prompt", "prompt for any AI", "works on ChatGPT and Claude", "universal prompt", "reusable prompt", or pastes a rough question and wants it sharpened first, even if they do not say the word "prompt". Especially useful for coding, research, studying, writing, and analysis questions.
---

# Prompt Refiner

Take the user's rough prompt, work out what they really want, and rebuild it as a prompt that any capable AI model will handle well. Then deliver it in the form the user needs.

## Step 1: Pick the mode

Read the request and choose one mode. If nothing says otherwise, use **Answer**.

| Mode | Trigger | Deliverable |
|---|---|---|
| **Answer** (default) | "refine", "/refine", or a rough question with no target model | Show the refined prompt briefly, then answer it in full |
| **Portable** | "for any AI", "to paste into", "reusable", "universal", "just give me the prompt" | The refined prompt only, in a copy-paste code block |
| **Tuned** | Names specific models or tools ("for ChatGPT and Gemini", "for Cursor", "for Midjourney") | One portable prompt plus a short tuned variant per named target |
| **Critique** | The user pastes a prompt they already wrote and asks for feedback or a score | Short scorecard, top fixes, and an improved version |

Switch modes when the user asks, for example "just answer" (Answer without showing the prompt) or "now give me the paste-ready version" (Portable).

## Step 2: Diagnose the rough prompt

Silently work out:

- **Task type**: coding, research, studying, writing, analysis, creative, data, planning, agent task, image or video generation.
- **Real goal**: the outcome the user wants, not just the words typed.
- **Gaps**: which of goal, context, audience, constraints, inputs, output format, and quality bar are missing.
- **Depth needed**:
  - *Light*: the prompt is already decent. Make minimal edits and say so.
  - *Standard*: most prompts. Fill the gaps and structure it.
  - *Deep*: complex or high-stakes tasks. Add steps, examples, verification, and edge cases.

## Step 3: Build the refined prompt

Use this portable blueprint. Include only the parts that apply, and keep them plain text so every model can read them:

```
Task: [one clear sentence saying what to do]
Context: [background, situation, what the user already knows or tried]
Audience and level: [who it is for, how technical]
Inputs: [material to work on, or a placeholder like [PASTE CODE HERE]]
Constraints: [scope, length, language, versions, things to avoid, stated positively]
Output format: [structure, length, code, table, sections]
Quality bar: [what "good" means, how to handle uncertainty]
```

Rules for building it:

1. **Keep the user's intent.** Sharpen and clarify. Do not change the question or widen the scope.
2. **Never invent facts about the user.** Unknown personal details become a labelled assumption (Answer mode) or a `[PLACEHOLDER]` (Portable and Tuned modes).
3. **Use plain, model-neutral formatting.** Short labelled sections or simple Markdown headers. Do not rely on XML tags, special tokens, or one vendor's syntax in the portable version. Tuned variants may use them.
4. **State constraints positively.** Say what to do ("use plain language") rather than only what not to do.
5. **Add only what earns its place.** No filler personas, no "you are the world's best expert" padding. A role is useful only when it sets a real domain frame.
6. **Pick techniques on purpose.** See `references/techniques.md` for when to add examples, reasoning steps, decomposition, output schemas, or a self-check.
7. **Ask at most one question**, and only if a wrong guess would make the whole result useless. Otherwise assume and label it.

For task-type tuning and model-specific tendencies, read `references/models.md` when the task is a coding agent, search-grounded tool, image or video model, or reasoning model, or when the user names a target.

## Step 4: Self-check before delivering

Run this check silently and fix any failure:

- Could a stranger with no context follow this and produce what the user wants?
- Is every added detail something the user said, implied, or that is a clearly labelled assumption?
- Is the output format explicit?
- Is it as short as it can be while staying complete?
- Would it still work if pasted into a different model?

## Step 5: Deliver by mode

### Answer mode
**Refined prompt**
> [refined prompt, kept short]

*Assumptions:* [only if any, one line]

[Full answer to the refined prompt]

If the original was already clear and detailed, say so in one line and answer directly.

### Portable mode
```
[refined prompt, ready to paste]
```
**What changed:** 2 to 4 short bullets naming the biggest improvements.
**Fill in before use:** list any `[PLACEHOLDERS]`, only if there are any.

### Tuned mode
Give the portable prompt first, then a variant for each named target with one line on what was adjusted and why. Read `references/models.md` first. Say that model behavior changes over time, and that a precise setup for a specific version is worth checking against that model's current docs.

### Critique mode
Score the prompt out of 10 on clarity, context, constraints, and output format. List the top 3 fixes, then give the improved version in a code block.

## Boundaries

- Do not write prompts meant to bypass an AI's safety rules or to deceive people. Decline that part and help with the legitimate goal.
- Do not claim a prompt will guarantee a result. Prompts raise the odds of a good answer; they do not promise one.
- Keep the whole response proportionate. A one-line question does not need a page of scaffolding.
