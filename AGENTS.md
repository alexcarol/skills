# Agent guide for skills repo

## Repo structure

Each skill lives in its own folder at the repo root:

```
<skill-name>/
└── SKILL.md    # Required: frontmatter + instructions
```

## SKILL.md format

```markdown
---
name: <skill-name>
description: <one-line description — shown to users and used for auto-invocation matching>
user-invocable: true
allowed-tools: Bash
---

Instructions for the agent to follow when this skill is invoked.
```

Key frontmatter fields:
- `name` — matches the folder name and the `/slash-command` users type
- `description` — used by the agent to decide when to auto-invoke; be specific
- `user-invocable: true` — allows `/skill-name` invocation by the user
- `allowed-tools` — restrict which tools the skill may use

## Adding a new skill

1. Create a folder: `<skill-name>/SKILL.md`
2. Write clear step-by-step instructions in the body
3. Add a row to the table in `README.md`

## Modifying a skill

Edit only `<skill-name>/SKILL.md`. Do not rename folders without updating `README.md`.

## Conventions

- Instructions should be imperative and step-by-step
- Prefer `--yes`/`--global`/`--copy` flags when running `npx skills add` to avoid interactive prompts
- Keep skills focused on a single workflow; split unrelated concerns into separate skills
