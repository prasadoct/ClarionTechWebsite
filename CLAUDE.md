# CLAUDE.md — ClarionTechWebsite

This file provides context and conventions for AI assistants working in this repository.

## Repository Overview

This repository is a **website capture archive** for the ClarionTech company website (www.clariontech.com). It is **not** a traditional software development project — there is no application source code, build system, or test suite. The contents are static files exported from a live website using browser developer tools.

## Repository Structure

```
ClarionTechWebsite/
├── README.md                                                          # Minimal project heading
├── CLAUDE.md                                                          # This file
├── AI Software Development Company _ Hire Dedicated Developers.html  # Full HTML capture of the website (6022 lines, ~309KB)
└── AI Software Development Company _ Hire Dedicated Developers_files/
    └── 3852769(1).js.download                                         # HubSpot cookie/tracking script (~62KB)
```

## File Details

### HTML File
- **Path:** `AI Software Development Company _ Hire Dedicated Developers.html`
- **Size:** ~6022 lines, 309 KB
- **Content:** Complete HTML export of the ClarionTech homepage, including all inline styles, embedded scripts, and external resource references.
- **External dependencies referenced:**
  - HubSpot (portal ID: 3852769) — analytics, forms, and cookie consent
  - Google Tag Manager
  - Microsoft Clarity (session recording/heatmaps)
  - Facebook Pixel
  - Factors analytics
  - jQuery 1.11.2 + jQuery Migrate 1.2.1

### JavaScript File
- **Path:** `AI Software Development Company _ Hire Dedicated Developers_files/3852769(1).js.download`
- **Size:** ~62 KB, 15 lines (minified)
- **Content:** HubSpot portal cookie policy and privacy configuration scoped to `www.clariontech.com`.

## Git Configuration

| Property | Value |
|---|---|
| Default branch | `master` |
| Remote | `origin` (local proxy) |
| Current working branch | `claude/claude-md-mm90mktx9k4nnt4f-1QdiM` |

### Commit History

| Commit | Description | Date |
|---|---|---|
| `5538e8a` | Initial commit — added README.md | 2026-03-02 |
| `b480ff2` | Add files via upload — HTML capture | 2026-03-02 |
| `ae12bbf` | Add files via upload — HubSpot JS | 2026-03-02 |

Author: prasadoct <prasad.oct@gmail.com>

## Development Conventions

Since this is a static website archive rather than a software project, the following conventions apply:

### What This Repo Is For
- **Archiving** the current state of the ClarionTech public website
- **Reference** for design, content, or markup analysis
- **Baseline** for comparison if a new website or redesign is being developed

### What This Repo Is NOT For
- Running a web server (no build/serve scripts)
- Active feature development (no source code)
- Automated testing (no test framework)

### Making Changes
If you edit the HTML file, preserve the following:
- The overall document structure (`<!DOCTYPE html>`, `<head>`, `<body>` sections)
- Existing script and style block ordering (scripts may depend on load order)
- HubSpot portal ID references (`3852769`) — required for analytics/form tracking to function correctly
- External CDN URLs — do not change without verifying the new URL is valid

### No Build, Test, or Lint Commands
There are no scripts to run. The repository has:
- No `package.json`
- No `Makefile`
- No CI/CD pipeline (no `.github/workflows/`, no `Jenkinsfile`, etc.)
- No linter or formatter configuration

## Branch Strategy

- **`master`** — stable snapshot of the website
- **`claude/*`** — Claude AI session branches (e.g., `claude/claude-md-mm90mktx9k4nnt4f-1QdiM`)

Claude session branches should be merged into `master` (via pull request) after changes are reviewed.

## AI Assistant Guidelines

When working in this repository:

1. **Do not create unnecessary files.** This is a minimal archive; avoid adding boilerplate, configs, or tooling unless explicitly requested.
2. **Treat the HTML file as read-only by default.** Only modify it when the user explicitly asks for HTML edits.
3. **Do not attempt to run or serve the HTML.** There is no local server; the file is a static snapshot.
4. **Preserve external integrations.** Do not remove or alter HubSpot, Google, or other analytics scripts without explicit instruction.
5. **Commit messages should be descriptive.** Since history is minimal, clear commit messages help track what changed and why.
6. **Push to the correct branch.** All Claude work goes to the `claude/` branch specified at session start, never directly to `master`.
