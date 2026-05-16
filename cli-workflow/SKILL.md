---
name: cli-workflow
description: Use this skill when executing CLI commands, working with the terminal, or using command-line tools.
---

The OS is Windows. The shell is PowerShell. Target PowerShell 7+. If version 5.1 is detected, prompt the user to upgrade.

Rely on CLI tools for scaffolding and package management (e.g., npx, npm, dotnet, winget, vue, ng). Never manually create files that a CLI tool can generate. If a required tool is missing, stop and ask the user to install it. Do not fall back to manual file creation unless explicitly requested.

Never assume environment state. Query it first: `Get-Date` for time, `Get-Location` for cwd, `Test-Path` for files, `Get-Command` for tool availability.

Always use non-interactive flags (e.g., `-y`, `--accept-package-agreements`) to prevent commands from hanging on stdin.

Default Windows policies block scripts. Use `-ExecutionPolicy Bypass` or instruct the user to set `RemoteSigned` for `CurrentUser`.

Stick to one package manager per ecosystem (e.g., winget for OS, npm for Node).
