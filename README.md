# freqtrade-tools

[![ClawHub Skill](https://img.shields.io/badge/ClawHub-Skill-blue)](https://clawhub.ai/djc00p/skills/freqtrade-tools)

Shell aliases and helper commands for Freqtrade (cryptocurrency trading bot) that speed up common tasks. Use when setting up Freqtrade shortcuts, downloading market data quickly, running backtests from the command line, or controlling the bot. ⚠️ Bot control commands (ftstart/ftstop/ftrestart) target a single named compose project and refuse to run against a live (dry_run: false) bot or delete cached data without explicit confirmation. Covers bash/zsh (Linux/macOS) and PowerShell/Command Prompt (Windows). Trigger phrases: freqtrade aliases, freqtrade shortcuts, ftdata, ftback, freqtrade commands, freqtrade windows.

---

## Install

Install from ClawHub:

```bash
clawhub install freqtrade-tools
```

Or clone this repo and add the skill folder to your agent's skills path.

## Usage

This skill activates automatically when a request matches its description.
See `SKILL.md` for the full instructions the agent follows.

## Repository layout

```
SKILL.md      # agent instructions
LICENSE       # MIT-0 / MIT
README.md     # this file
```

## Versions

Releases track the published ClawHub versions.

| Version | ClawHub |
| --- | --- |
| 1.0.7 | [freqtrade-tools v1.0.7](https://clawhub.ai/djc00p/skills/freqtrade-tools) |

---

**Published by [@djc00p](https://github.com/djc00p)**
