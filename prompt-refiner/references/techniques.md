# Prompt techniques: when to use each

Use a technique only when it helps the task. More is not better.

| Technique | Use when | Skip when |
|---|---|---|
| **Clear task sentence** | Always | Never skip |
| **Context and audience** | The answer depends on who it is for or what situation it is in | The question is self-contained |
| **Explicit output format** | The result will be parsed, reused, compared, or must be a specific shape | A short chat answer is fine |
| **Examples (few-shot)** | You need a specific style, format, or edge-case behavior. 1 to 3 short examples | The task is simple, or the model is a reasoning model that does better with a goal than with examples |
| **Step-by-step reasoning** | Math, logic, debugging, multi-part analysis on a standard chat model | Reasoning-focused models that already think internally. Ask for a clear final answer with brief justification instead |
| **Decomposition** | The task has several distinct parts. Number them and ask for each | A single simple question |
| **Ask-first clarification** | The task is open-ended and missing inputs would derail it | The user wants a fast draft |
| **Grounding** ("use only the text below") | Summaries and extraction from provided material, to cut invention | General knowledge questions |
| **Uncertainty handling** ("say when you are unsure, do not guess") | Facts, citations, numbers, medical, legal, or financial topics | Creative tasks |
| **Self-check** ("verify against the constraints before answering") | High-stakes or multi-constraint outputs | Casual questions |
| **Delimiters** (headers, triple quotes, clear separators) | Long inputs, pasted code or documents, several instructions | Short prompts |
| **Persona / role** | It sets a real domain frame, such as "act as a code reviewer for a security audit" | As decoration |

## Common weak spots to fix in rough prompts

- **Vague verb**: "help with", "look at", "do something about" -> name the action (explain, compare, rewrite, debug, outline).
- **Missing audience**: add level and purpose.
- **Missing format**: say how long and in what shape.
- **Hidden constraints**: language, framework, version, deadline, tone.
- **Bundled tasks**: split into numbered parts.
- **No success test**: say what a good answer looks like.
- **Conflicting instructions**: resolve them or ask the one question that settles it.
