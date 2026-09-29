# Model and tool tendencies

These are general tendencies, not guarantees. Models and products change often. If the user names an exact model version and precision matters, suggest checking that model's current documentation.

The **portable prompt** (plain labelled sections) is the safe default for every model below. Use these notes only for Tuned mode or when the target is clear.

## General chat models
- **Claude-style models**: follow clear, direct instructions well. XML-style tags can help separate instructions from pasted material. For long documents, put the material first and the question last. Explaining the reason behind a constraint tends to help.
- **GPT-style models**: respond well to structured Markdown sections, clear delimiters, and an explicit output format. Keep system-level rules (tone, format) separate from the task when the interface allows it.
- **Gemini-style models**: handle long context and mixed material well. Put the context first and the instruction after it, and state the output format explicitly. Examples help.
- **Open-weight models (Llama, Mistral, Qwen, and similar)**: prefer shorter, explicit prompts, one task at a time, a stated output format, and one or two examples. Instruction-following varies by size, so keep constraints few and clear.

## Reasoning-focused models
Models that reason internally (often marketed as "thinking" or "reasoning" models) usually do best with a clear goal, the constraints, and the definition of done. Avoid heavy step-by-step scaffolding and many examples. Ask for a final answer with a brief justification.

## Search-grounded tools (Perplexity-style)
Ask one specific question per prompt. Include the topic, time frame, and region. Ask for sources. Skip role-play and long instructions.

## Coding assistants and agents (Cursor, Copilot, Claude Code, and similar)
Include the file paths or module names, the language and version, the exact behavior wanted, acceptance criteria (tests that should pass), and boundaries ("do not change the public API"). State whether to explain, fix, or refactor. Ask for small, reviewable changes.

## Image models
Describe the subject, setting, style, composition or camera angle, lighting, mood, and aspect ratio. Use concrete visual words instead of abstract ones. Some tools support negative prompts or special parameters; only include those if the user names the tool, and mention the syntax varies by tool.

## Video models
Describe the subject, the action over time, camera movement, setting, style, and duration. Keep it to one scene per prompt.

## Writing and creative tasks
State the audience, tone, length, and point of view. Give one short style sample if the user has one. Say what to avoid (clichés, jargon) in positive terms where possible.
