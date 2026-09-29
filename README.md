# prompt-refiner

A Claude skill that turns a rough, short, or vague prompt into a clear, detailed, well-structured prompt that works on **any AI model**, then either answers it or hands it back ready to paste.

Works with Claude, ChatGPT, Gemini, Llama, Mistral, DeepSeek, Qwen, Perplexity, coding agents, and image or video generators. Especially useful for coding, research, studying, writing, and analysis questions.

## Modes

| Mode | How to trigger | What you get |
|---|---|---|
| **Answer** (default) | `/refine ...` or a rough question | The refined prompt, shown briefly, then a full answer to it |
| **Portable** | "for any AI", "just give me the prompt", "reusable" | Only the refined prompt, in a copy-paste block that works on any model |
| **Tuned** | Name targets: "for ChatGPT and Gemini", "for Cursor" | A portable prompt plus a short tuned variant per named model or tool |
| **Critique** | "critique this prompt: ..." | A score, the top 3 fixes, and an improved version |

Say **"just answer"** to skip showing the refined prompt in Answer mode.

## How it works

1. **Diagnose**: task type, real goal, missing pieces, and how much depth the prompt needs (light, standard, or deep).
2. **Build** with a plain-text blueprint that any model can read: Task, Context, Audience, Inputs, Constraints, Output format, Quality bar.
3. **Choose techniques on purpose**: examples, step-by-step reasoning, decomposition, grounding, or a self-check, only when they help.
4. **Self-check**: could a stranger follow this, is every added detail from you or a labelled assumption, does it still work on another model.
5. **Deliver** in the chosen mode.

## Install

### Claude.ai (web / desktop / mobile)
1. Download `prompt-refiner.skill` from the [Releases](../../releases) page.
2. Open it in Claude and click **Save skill**, or upload it under **Settings > Capabilities > Skills**. Your plan or organization must allow custom skills.

### Claude Code
```bash
# personal (all projects)
mkdir -p ~/.claude/skills
cp -r prompt-refiner ~/.claude/skills/

# or project-only
mkdir -p .claude/skills
cp -r prompt-refiner ~/.claude/skills/
```

## Usage

```
/refine explain recursion
refine for any AI: summarize a research paper
give me a version for ChatGPT and Gemini: plan a study schedule
critique this prompt: Write me a good essay about climate
```

See [`examples/examples.md`](examples/examples.md) for full before and after samples.

## Rules the skill follows

- Keeps your original intent and never widens the scope.
- Never invents facts about you. Unknowns become labelled assumptions or `[PLACEHOLDERS]`.
- Asks at most one clarifying question, and only if a wrong guess would ruin the result.
- Keeps the rewrite short and free of filler personas.
- Will not write prompts meant to bypass an AI's safety rules or to deceive people.

## Repo layout

```
prompt-refiner/                 (repo root)
├── README.md
├── LICENSE
├── .gitignore
├── prompt-refiner.skill        # packaged skill, ready to upload
├── prompt-refiner/
│   ├── SKILL.md                # workflow, modes, rules
│   └── references/
│       ├── techniques.md       # when to use each prompting technique
│       └── models.md           # tendencies by model family and tool type
└── examples/
    └── examples.md
```

## Customizing

- Edit `prompt-refiner/SKILL.md` to change modes, rules, or the output shape.
- The `description` in the frontmatter controls when the skill triggers. Add or remove trigger phrases there.
- Edit `references/models.md` as models change. Its notes are general tendencies, not guarantees, so check a model's current docs when precision matters.

## Packaging

```bash
cd prompt-refiner && zip -r ../prompt-refiner.skill . && cd ..
```

Or use the skill-creator packaging script if you have it.

## License

MIT. See [LICENSE](LICENSE).
