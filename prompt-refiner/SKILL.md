---
name: prompt-refiner
description: Takes the user's rough, short, or vague prompt, rewrites it into a well-structured, detailed, contextualized prompt, and then answers that improved prompt in the same response. Use whenever the user says "refine", "/refine", "improve my prompt and answer it", "make this prompt better then answer", "polish this then respond", or pastes a rough question and asks Claude to sharpen it first. Especially useful for coding, research, and studying questions. This is NOT for writing prompts for other AI tools; the refined prompt is used by Claude itself to give a better answer.
---

# Prompt Refiner

Turn a rough prompt into a strong one, then answer the strong one.

## Workflow

1. **Read the rough prompt** and work out the real goal behind it: what the user wants to end up with, not just what they typed.
2. **Rewrite it** as a detailed, contextualized prompt (see the checklist below).
3. **Show the refined prompt** briefly, in a quote block, under a short heading like "Refined prompt".
4. **Answer the refined prompt** fully, right after it. This is the main deliverable, so do not stop after the rewrite.

## What a good refined prompt contains

Include only what applies. Do not pad.

- **Goal**: the specific outcome wanted, stated plainly.
- **Context**: relevant background from the conversation, files, or stated preferences. Never invent facts about the user. If something is unknown, say so or make a labelled assumption.
- **Role and audience**: who the answer is for (e.g. a beginner, an exam candidate, a working developer) and what level to pitch it at.
- **Scope and constraints**: language, framework, version, length, things to avoid, time limits.
- **Depth and format**: what the answer should look like (code with comments, step-by-step explanation, comparison table, summary plus details, practice questions).
- **Quality bar**: what makes the answer good (correct, tested, sourced, explained with examples).

## Domain tuning

- **Coding**: add language and version, environment, expected input and output, error messages, edge cases, and whether the user wants a fix, an explanation, or both. Prefer working code with a short explanation of why it works.
- **Research**: add the question's scope, time frame, what counts as a good source, and whether to compare viewpoints. Use web search for anything current and cite sources.
- **Studying**: add the topic, level, exam or course context, and the learning goal. Prefer clear explanations with examples, then offer a quiz or flashcards.

## Rules

- **Keep the original intent.** Sharpen the prompt; do not change what the user is asking or widen the scope.
- **Do not stall.** If the prompt is missing something important, make a reasonable assumption, label it in one line ("Assuming Python 3.11"), and answer. Ask at most one clarifying question, and only if a wrong guess would make the whole answer useless.
- **Keep the rewrite short.** The refined prompt should usually be a paragraph or a few lines, not a long essay. The value is in the answer.
- **Answer the refined prompt, not the rough one.** The response should reflect the added detail.
- **Silent mode.** If the user says "just answer" or "don't show the refined prompt", skip step 3 and only give the improved answer.
- **Already-good prompts.** If the prompt is already clear and detailed, say so in one line and just answer it.

## Output shape

**Refined prompt**
> [the rewritten prompt]

*Assumptions:* [only if any]

[The full answer]
