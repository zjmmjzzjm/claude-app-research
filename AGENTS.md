# AGENTS.md - AI Agent Guidelines for iOS App Ecosystem Research Repository

> This file provides context and guidelines for AI coding agents operating in this repository.

## Project Overview

This is a **knowledge management and research repository** for systematic iOS App ecosystem research. It focuses on:
- App distribution, privacy, advertising, payments
- Risk control, data collection, networking, security
- Reusable methodologies and experimental scripts

**Important**: This is NOT a traditional software project. It's a documentation and research archive.

---

## Repository Structure

```
docs/                     # Overview docs: research scope, methodology, standards
research/
  apps/                   # App-centric research files (one per app)
    _template/            # Template for new app research
  topics/                 # Topic-centric knowledge (privacy, payments, ads, security)
  experiments/            # Reproducible experiments (packet capture, reverse engineering)
artifacts/                # Large/binary/traceable outputs
  ipa/                    # iOS application binaries
  traffic-captures/       # Network packet captures (pcap)
  screenshots/            # App screenshots
  reports/                # Analysis reports (markdown)
data/                     # Structured data (CSV/JSON/SQLite)
tools/                    # Tools and scripts
  scripts/                # General utility scripts
  frida/                  # Frida dynamic instrumentation scripts
  mitmproxy/              # Traffic interception scripts
references/               # Reference materials index (papers, articles, links)
templates/                # Reusable templates (interview guides, checklists)
```

---

## Build/Lint/Test Commands

This repository has **no build system** - it's primarily Markdown documentation.

### Available Tools (if scripts exist)

```bash
# Python scripts (if present in tools/scripts/)
python tools/scripts/<script-name>.py

# Frida scripts (requires Frida installed)
frida -U -f <bundle-id> -l tools/frida/<script>.js

# mitmproxy scripts
mitmproxy -s tools/mitmproxy/<script>.py
```

### Validation Commands

```bash
# Check markdown files for broken links (if markdownlint installed)
markdownlint '**/*.md'

# Validate JSON data files
python -m json.tool data/*.json

# Git status check
git status
```

---

## Code Style Guidelines

### Markdown Files

1. **Language**: Use Chinese for research documentation (matches existing content)
2. **Headings**: Use ATX-style headers (`#`, `##`, `###`)
3. **Line length**: Keep lines under 120 characters for readability
4. **Code blocks**: Always specify language for syntax highlighting
5. **Tables**: Use Markdown tables for structured comparisons
6. **Links**: Use relative paths for internal references

### Naming Conventions

| Type | Convention | Example |
|------|------------|---------|
| App directory | `<app-name>` or `<bundle-id>` | `research/apps/wechat/` |
| Experiment directory | `<date>-<topic>-<short-title>/` | `research/experiments/20251222-privacy-tracking/` |
| Artifact files | `YYYYMMDD_<app>_<scene>_<type>` | `20251222_wechat_login_pcap` |
| Report files | Descriptive kebab-case | `opencode-analysis.md` |

### Python Scripts (tools/)

```python
# Use type hints
def analyze_traffic(pcap_path: str) -> dict:
    pass

# Use docstrings
"""
Brief description.

Args:
    pcap_path: Path to the packet capture file.

Returns:
    Analysis results dictionary.
"""

# Imports order: stdlib, third-party, local
import os
import json

import frida
import mitmproxy

from .utils import helper
```

### JavaScript/Frida Scripts

```javascript
// Use strict mode
'use strict';

// Descriptive function names
function hookNetworkRequest() {
    // Implementation
}

// Document hooking targets
// Target: -[NSURLSession dataTaskWithRequest:completionHandler:]
```

---

## File Organization Rules

### When Creating New Research

1. **New App Research**: Copy `research/apps/_template/` to `research/apps/<app-name>/`
2. **New Topic**: Create directory under `research/topics/<topic-name>/`
3. **New Experiment**: Create `research/experiments/<YYYYMMDD>-<topic>-<title>/`

### Artifact Management

- **Large files** (IPA, pcap): Place in `artifacts/` subdirectories
- **Reports**: Place in `artifacts/reports/` as Markdown
- **Screenshots**: Place in `artifacts/screenshots/` with descriptive names
- **Always reference** artifact paths in research documents

---

## Error Handling

### For Scripts

```python
# Always handle file operations gracefully
try:
    with open(path, 'r', encoding='utf-8') as f:
        data = json.load(f)
except FileNotFoundError:
    logger.error(f"File not found: {path}")
    raise
except json.JSONDecodeError as e:
    logger.error(f"Invalid JSON in {path}: {e}")
    raise
```

### For Documentation

- Mark incomplete sections with `TODO:` or `WIP:`
- Note data sources and retrieval dates
- Flag unverified claims with `[未验证]`

---

## Git Workflow

### Commit Message Format

```
<type>: <short description in Chinese or English>

Types:
- docs: Documentation changes
- research: New research content
- tools: Script/tool changes
- data: Data file updates
- fix: Corrections to existing content
```

### Examples

```bash
git commit -m "docs: 添加 OpenCode 项目分析报告"
git commit -m "research: 新增独立开发方法论文档"
git commit -m "tools: 添加 Frida 网络请求 Hook 脚本"
```

---

## Permissions (from .claude/settings.local.json)

Allowed operations for AI agents:
- Python script execution
- Playwright browser automation
- Pandoc document conversion
- Git operations (add, commit, push)
- Web fetching from: github.com, raw.githubusercontent.com, opencode.ai

---

## Important Notes for AI Agents

1. **This is a research archive** - Focus on documentation quality over code
2. **Preserve Chinese content** - Most research docs are in Chinese
3. **Reference existing patterns** - Check `artifacts/reports/` for report style
4. **Use templates** - Always start from `_template/` for new app research
5. **Link artifacts** - When mentioning files, include relative paths
6. **Cite sources** - Include URLs and dates for external references
7. **No sensitive data** - Never commit API keys, credentials, or PII

---

## Quick Reference

| Task | Location |
|------|----------|
| Start new app research | Copy `research/apps/_template/` |
| Add analysis report | `artifacts/reports/<name>.md` |
| Store traffic capture | `artifacts/traffic-captures/` |
| Add methodology docs | `research/topics/` |
| Utility scripts | `tools/scripts/` |
