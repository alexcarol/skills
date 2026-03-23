# skills

A collection of Claude Code skills.

## Installation

Install all skills globally using [npx skills](https://npmjs.com/package/skills):

```bash
npx skills add alexcarol/skills --global --copy
```

Or install into a specific project:

```bash
npx skills add alexc/skills
```

### Manual installation

Copy any skill folder into `~/.claude/skills/` (global) or `.claude/skills/` (project-local):

```bash
cp -r pr ~/.claude/skills/pr
```

## Skills

| Skill | Description |
|-------|-------------|
| [`pr`](./pr) | Commit all changes and open a pull request. Creates a branch first if on main/master. |

## Usage

Invoke a skill with `/skill-name` in Claude Code:

```
/pr
/pr my-feature-branch
```
