---
name: git-commit
description: Use this skill when committing changes with git.
metadata:
    github-repo: https://github.com/netsentinel/copilot-recipes
---

Create standardized commits using the Conventional Commits specification. Analyze the diff to determine type, scope, and message.

## Conventional Commit Format

```text
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

- **Header**: `<type>[scope]: <description>`. Must be present tense, imperative mood, under 72 characters.
- **Body**: Detailed explanation of *why* the change was made. No strict character limit.
- **Footer**: `BREAKING CHANGE: <description>` and/or issue references (`Closes #123`, `Refs #456`).

## Commit Types

`feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`

## Workflow

1. Analyze the diff (`git diff --staged` or `git diff`). Stage changes if needed, but never commit secrets.
2. Generate a commit message.
3. Use multiple (from one to three) `-m` flags. Git maps arguments sequentially: header, body, footer; inserting blank lines between them automatically.

## Breaking Changes

Indicate by adding `!` after the type/scope (e.g., `feat!:`) or by adding a `BREAKING CHANGE:` footer.

## Safety Protocol

- Never commit secrets (.env, credentials, private keys, etc.).
- Never use `--no-verify` unless explicitly requested.
- Never force push to main/master.
- Never use destructive commands (--force, hard reset) without explicit request.
- If commit fails due to hooks, fix and create a new commit (do not amend).
