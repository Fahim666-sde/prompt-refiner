# prompt-refiner

A Claude skill that takes a rough, short, or vague prompt, rewrites it into a well-structured, detailed, contextualized prompt, and then **answers that improved prompt** in the same response.

It is not a prompt generator for other AI tools. Claude uses the refined prompt itself to give you a better answer.

## What it does

1. Works out the real goal behind your rough prompt.
2. Rewrites it with goal, context, audience, constraints, format and quality bar.
3. Shows the refined prompt in a short quote block.
4. Answers the refined prompt in full.

Tuned for **coding**, **research** and **studying** questions.

## Install

### Claude.ai (web / desktop / mobile)
1. Download `prompt-refiner.skill` from the [Releases](../../releases) page (or zip the `prompt-refiner/` folder yourself so `SKILL.md` sits inside a `prompt-refiner/` directory).
2. Open the file in Claude and click **Save skill**, or go to **Settings > Capabilities > Skills** and upload it. Your plan or organization must allow custom skills.

### Claude Code
Copy the skill folder into your skills directory:

```bash
# personal (all projects)
mkdir -p ~/.claude/skills
cp -r prompt-refiner ~/.claude/skills/

# or project-only
mkdir -p .claude/skills
cp -r prompt-refiner .claude/skills/
```

## Usage

Start a message with a trigger phrase, then your rough prompt:

```
/refine explain recursion
refine: fix my python error, it says list index out of range
improve my prompt then answer it: how do transformers work
```

Options:
- Say **"just answer"** or **"don't show the refined prompt"** to skip the rewrite and only get the improved answer.
- If your prompt is already clear and detailed, the skill says so and answers directly.

## Behavior rules

- Keeps your original intent and does not widen the scope.
- Makes labelled assumptions instead of stalling. Asks at most one clarifying question, and only if a wrong guess would ruin the answer.
- Keeps the rewrite short. The answer is the main deliverable.
- Never invents facts about you.

See [`examples/`](examples) for before/after samples.

## Repo layout

```
prompt-refiner/
├── README.md
├── LICENSE
├── .gitignore
├── prompt-refiner/
│   └── SKILL.md        # the skill itself
└── examples/
    └── examples.md
```

## Customizing

Edit `prompt-refiner/SKILL.md`. The `description` in the frontmatter controls when the skill triggers, so add or remove trigger phrases there. The body controls the workflow and rules.

## License

MIT. See [LICENSE](LICENSE).
