# ⚡ Freqtrade Tools: Developer Productivity Suite

[![ClawHub Skill](https://img.shields.io/badge/ClawHub-Skill-blue)](https://clawhub.ai/djc00p/freqtrade-tools) [![Agent Skill](https://img.shields.io/badge/Agent-Skill-blue)](#) [![Freqtrade Crypto Trading](https://img.shields.io/badge/Freqtrade-Crypto_Trading-green)](https://github.com/freqtrade/freqtrade)

**Streamline your Freqtrade (Crypto Trading Bot) workflow with high-velocity shell aliases and helper functions.**

Managing a Freqtrade instance involves repetitive tasks: downloading market data, running backtests, managing Docker containers, and monitoring logs. The **Freqtrade Tools** suite offers a set of optimized shell functions for **Bash/Zsh (Linux/macOS)** and **PowerShell (Windows)**, transforming complex, multi-flag Docker commands into simple, memorable aliases.

---

## 🚀 Quick Start

### 1. Installation

#### **For Linux & macOS (Bash or Zsh)**

1. Open your configuration file: `nano ~/.zshrc` (or `~/.bashrc`).
2. Copy the function definitions from `references/bash-zsh-aliases.md`.
3. Paste them at the bottom of your file and save.
4. Reload your shell: `source ~/.zshrc` (or `source ~/.bashrc`).

#### **For Windows (PowerShell)**

1. Open your PowerShell profile: `notepad $PROFILE`.
2. Copy the functions from `references/windows-equivalents.md`.
3. Paste them into the profile, save, and restart your terminal.

---

## 🛠 Core Command Reference

| Command | Purpose | Scope |
| :--- | :--- | :--- |
| `ftdata` | Download historical market data from Kraken | Data Management |
| `ftback` | Execute backtests on specific strategies | Strategy Testing |
| `ftstart` | Spin up all Docker Compose services | Bot Management |
| `ftstop` | Gracefully stop all Docker Compose services | Bot Management |
| `ftrestart` | Restart the entire trading stack | Bot Management |
| `ftlogs` | Stream live, real-time logs from the bot | Monitoring |
| `ftstatus` | Check container health + tail recent logs | Monitoring |
| `ftlist` | List all downloaded `.json` data files | Data Management |
| `ftui` | Automatically launch the Freqtrade UI in your browser | UI/UX |

---

## 📖 Deep Dives

### 📉 `ftdata` — Efficient Data Ingestion

The `ftdata` command autom_calculates date ranges and handles the complexities of Kraken's data requirements.

**Syntax:**
`ftdata <pair> [days] [timeframe] [--erase]`

**Examples:**

* **Standard Download:** `ftdata "BTC/USDT" 90 5m`
  *(Downloads 90 days of 5-minute candles for BTC/USDT)*
* **High Timeframe:** `ftdata "ETH/USDT" 30 1h`
  *(Downloads 30 days of 1-hour candles for ETH/USDT)*
* **The "Clean Slate" Mode:** `ftdata "SOL/USDT" 365 5m --erase`
  **⚠️ Critical:** Use `--erase` when extending a time range. Kraken requires data continuity; erasing existing data prevents "overlap errors" that corrupt your dataset.

---

### 🧪 `ftback` — Rapid Backtesting

Run backtests without typing long, cumbersome `docker-compose exec` strings.

**Syntax:**
`ftback <strategy_name> [days] [timeframe] [pair]`

**Examples:**

* **Quick Test:** `ftback "MyStrategy" 60 5m`
  *(Tests MyStrategy for the last 60 days using 5m candles)*
* **Targeted Pair Test:** `ftback "MyStrategy" 90 1h "BTC/USDT"`
  *(Tests a specific pair on a higher timeframe)*

---

## 🛡 Best Practices & Safety

1. **Container Awareness:** All `ft` commands (except `ftdata` and `ftback`) rely on **Docker Compose**. Ensure your `docker-compose.yml` is in the directory where you execute these commands.
2. **Data Integrity:** Always use the `--erase` flag when you are expanding the historical window of an existing pair to avoid data fragmentation.
3. **Resource Management:** Use `ftstop` before performing major system updates to ensure no

---
**Original implementation by [@djc00p](https://github.com/djc00p)**
