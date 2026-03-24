---
name: pr
description: Open a pull request. Only invoke when the user explicitly asks to open, create, or raise a PR or pull request — not for plain commits or pushes.
user-invocable: true
allowed-tools: Bash
---

You are helping the user commit their changes and open a pull request. Follow these steps:

## Step 1 — Check current branch

Run `git branch --show-current` to get the current branch.

If the branch is `main` or `master`:
- Look at the staged/unstaged changes to come up with a short, descriptive branch name (kebab-case, e.g. `add-dark-mode` or `fix-login-bug`)
- If the user passed arguments, use those as the branch name
- Create and switch to the new branch: `git checkout -b <branch-name>`

If already on a feature branch, stay on it.

## Step 2 — Commit

Follow the standard commit protocol:
1. Run `git status` and `git diff` to review all changes
2. Stage relevant files (avoid `.env`, secrets, large binaries)
3. Write a concise commit message focused on *why*, not *what*
4. Commit

## Step 3 — Push
Push the branch to the intended remote

## Step 4 — Open PR

Create the PR with `gh pr create`. If possible use an existing PR template, if none there use this format:
- Title: short (under 70 chars), imperative mood
- Body: 1-3 bullet summary + test plan checklist

```
gh pr create --title "<title>" --body "$(cat <<'EOF'
## Summary
- <bullet points>

## Test plan
- [ ] <test steps>
EOF
)"
```

Return the PR URL to the user when done.
