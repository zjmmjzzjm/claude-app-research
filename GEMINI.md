# GEMINI.md - iOS App Ecosystem Research Context

## Project Overview

This is a **knowledge management and research repository** dedicated to the systematic study of the iOS App ecosystem.
It covers areas such as app distribution, privacy, advertising, payments, risk control, data collection, networking, and security.

**Project Type:** Non-Code / Research Archive (with supporting scripts)
**Primary Language:** Chinese (for documentation)

---

## Directory Structure

| Directory | Purpose |
| :--- | :--- |
| `docs/` | Overview documentation: scope, methodology, standards. |
| `research/apps/` | App-centric research files. Each app gets its own folder (e.g., `research/apps/wechat/`). |
| `research/apps/_template/` | Template for creating new app research archives. |
| `research/topics/` | Topic-centric knowledge (e.g., privacy, payments, security). |
| `research/experiments/` | Reproducible experiments (e.g., packet capture analysis, reverse engineering). |
| `artifacts/` | Large/binary/traceable outputs (IPA files, pcaps, screenshots, reports). |
| `data/` | Structured data (CSV/JSON/SQLite). |
| `tools/` | Utility scripts and tools. |
| `tools/frida/` | Frida dynamic instrumentation scripts (`.js`). |
| `tools/mitmproxy/` | Traffic interception scripts (`.py`). |
| `tools/scripts/` | General Python utility scripts. |
| `references/` | Index of reference materials (papers, articles, links). |
| `templates/` | Reusable templates (interview guides, checklists). |

---

## Key Workflows

### 1. New App Research
To start researching a new app:
1.  Copy the template: `cp -r research/apps/_template research/apps/<app-name>`
2.  Fill in the details according to the template structure.

### 2. New Topic Research
Create a new directory or document under `research/topics/` (e.g., `research/topics/privacy/`).

### 3. Artifact Management
*   **Location:** Store large files, screenshots, and reports in the `artifacts/` directory.
*   **Naming:** `YYYYMMDD_<app>_<scene>_<type>` (e.g., `20251222_wechat_login_pcap`).
*   **Referencing:** Always reference artifacts in your research markdown files using relative paths.

### 4. Running Tools
*   **Python Scripts:** `python tools/scripts/<script-name>.py`
*   **Frida:** `frida -U -f <bundle-id> -l tools/frida/<script>.js`
*   **Mitmproxy:** `mitmproxy -s tools/mitmproxy/<script>.py`

---

## Development & Documentation Conventions

### Documentation Style
*   **Language:** Chinese (Simplified).
*   **Format:** GitHub Flavored Markdown.
*   **Headers:** ATX-style (`#`, `##`).
*   **Links:** Use relative paths.

### Naming Conventions
*   **App Directory:** `<app-name>` or `<bundle-id>`
*   **Experiment Directory:** `<date>-<topic>-<short-title>/`
*   **Report Files:** Descriptive kebab-case (e.g., `opencode-analysis.md`).

### Git Commit Messages
Format: `<type>: <short description>`

**Types:**
*   `docs`: Documentation changes
*   `research`: New research content
*   `tools`: Script/tool changes
*   `data`: Data file updates
*   `fix`: Corrections

**Example:** `git commit -m "research: add Trae sleep audio analysis guide"`

---

## Key Files to Reference

*   **`AGENTS.md`**: detailed guidelines for AI agents (read this for specific constraints).
*   **`README.md`**: Project entry point and high-level guide.
*   **`research/topics/trae-sleep-audio-analysis.md`**: Example of a topic research document.
