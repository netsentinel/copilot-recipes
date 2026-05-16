---
name: cli-workflow
description: Use this skill when executing CLI commands, working with the terminal, or using command-line tools.
metadata:
    github-repo: https://github.com/netsentinel/copilot-recipes
---

The OS is Windows. The shell is PowerShell. Target PowerShell 7+. If an older version is detected, prompt the user to upgrade.

Rely on CLI tools for scaffolding and package management (e.g., npx, npm, dotnet, winget, vue, ng, etc.). Never manually create files that a CLI tool can generate. If a required tool is missing, stop and ask the user to install it. Do not fall back to manual file creation unless explicitly asked.

Never assume environment state. Query it first if needed: `Get-Date` for time, `Get-Location` for cwd, `Test-Path` for files, `git status` for repo state, `dotnet --list-sdks` for dotnet version, etc.

Always use non-interactive flags (e.g., `-y`, `--accept-package-agreements`, etc.) to prevent commands from hanging on stdin.

Default Windows policies block scripts. Use `-ExecutionPolicy Bypass` or instruct the user to set `RemoteSigned` for `CurrentUser`.

Stick to one package manager per ecosystem (e.g., winget for OS, npm for Node, etc.).
