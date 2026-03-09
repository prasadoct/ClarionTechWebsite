# CLAUDE.md — ClarionTechWebsite

This file provides context and conventions for AI assistants working in this repository.

## Repository Overview

This repository is a **website capture and development archive** for the ClarionTech company website (www.clariontech.com). It contains a static export of the live homepage plus hand-crafted landing pages built to match the ClarionTech visual identity. There is no application source code, build system, or test suite.

## Repository Structure

```
ClarionTechWebsite/
├── README.md                                                          # Minimal project heading
├── CLAUDE.md                                                          # This file
├── AI Software Development Company _ Hire Dedicated Developers.html  # Full HTML capture of homepage (6021 lines, ~309 KB)
├── AI Software Development Company _ Hire Dedicated Developers_files/
│   └── 3852769(1).js.download                                         # HubSpot cookie/tracking script (~62 KB, 14 lines minified)
└── accelq-landing.html                                                # ACCELQ technology partner landing page (1491 lines, ~56 KB)
```

## File Details

### Main Homepage Capture
- **Path:** `AI Software Development Company _ Hire Dedicated Developers.html`
- **Size:** 6021 lines, ~309 KB
- **Content:** Complete browser export of the ClarionTech homepage, including all inline styles, embedded scripts, and external resource references.
- **External dependencies referenced:**
  - HubSpot (portal ID: `3852769`) — analytics, forms, and cookie consent
  - Google Tag Manager
  - Microsoft Clarity (session recording / heatmaps)
  - Facebook Pixel
  - Factors analytics
  - jQuery 1.11.2 + jQuery Migrate 1.2.1

### HubSpot Script
- **Path:** `AI Software Development Company _ Hire Dedicated Developers_files/3852769(1).js.download`
- **Size:** ~62 KB, 14 lines (minified)
- **Content:** HubSpot portal cookie policy and privacy configuration scoped to `www.clariontech.com`.

### ACCELQ Landing Page
- **Path:** `accelq-landing.html`
- **Size:** 1491 lines, ~56 KB
- **Content:** Standalone technology-partner landing page for ACCELQ (AI-powered test automation). Built from scratch to match the ClarionTech brand identity — it is **not** a browser capture.
- **Key characteristics:**
  - Self-contained single HTML file (all CSS inline in `<style>` blocks, no external JS dependencies)
  - Uses the ClarionTech font stack: `Nunito Sans`, `Raleway`, `Inter` (loaded from Google Fonts)
  - Follows the ClarionTech CSS variable palette (see Design Conventions below)
  - `lang="en-us"`, `charset="UTF-8"`, responsive viewport meta
  - No analytics or tracking scripts

## Design Conventions (for new landing pages)

When creating additional landing pages that must match the ClarionTech visual identity, follow these conventions established in `accelq-landing.html`:

### CSS Variables
```css
:root {
  --orange:    #f45f3e;   /* primary CTA / accent */
  --orange2:   #fb9860;   /* secondary accent */
  --gradient:  linear-gradient(90deg, #f45f3e, #fb9860);
  --dark:      #1d1d1d;
  --dark2:     #2d2d2d;
  --dark3:     #313030;
  --text:      #1c1c1c;
  --text-mid:  #444;
  --text-soft: #666;
  --border:    #d2d2d2;
  --bg-light:  #f9f9f9;
}
```

### Typography
- **Headings:** `Nunito Sans` (primary), `Raleway` (fallback)
- **Body / UI:** `Nunito Sans` (primary), `Inter` (fallback), `sans-serif`
- Load via Google Fonts: `Nunito+Sans:ital,opsz,wght@0,6..12,400;...` + `Raleway` + `Inter`

### Layout
- Max content width: `1180px` via `.content-wrapper { max-width: 1180px; margin: 0 auto; padding: 0 20px; }`
- Box-sizing: `*, *::before, *::after { box-sizing: border-box; }`
- Favicon: `https://www.clariontech.com/hubfs/Favicon-1.png`

### Buttons
- Primary CTA: gradient background (`--gradient`), white text, `border-radius: 4px`
- Outline variant: transparent background, gradient border via CSS trick

## Git Configuration

| Property | Value |
|---|---|
| Default branch | `master` |
| Remote | `origin` (local proxy) |
| Author | prasadoct \<prasad.oct@gmail.com\> |

### Commit History

| Commit | Description | Author | Date |
|---|---|---|---|
| `7077226` | Merge PR #1 from previous Claude session branch | prasadoct | 2026-03-02 |
| `a833087` | Add ACCELQ technology partner landing page | Claude | 2026-03-02 |
| `95eaa38` | Add CLAUDE.md with comprehensive repository analysis | Claude | 2026-03-02 |
| `ae12bbf` | Add files via upload — HubSpot JS | prasadoct | 2026-03-02 |
| `b480ff2` | Add files via upload — HTML capture | prasadoct | 2026-03-02 |
| `5538e8a` | Initial commit — added README.md | prasadoct | 2026-03-02 |

### Branch Strategy

- **`master`** — stable snapshot; merges happen via pull request after review
- **`claude/*`** — Claude AI session branches (e.g., `claude/claude-md-mmisai7ci4t7nx4z-biqKT`)

Claude session branches are merged into `master` via PR. Never push directly to `master`.

## Development Conventions

### What This Repo Is For
- **Archiving** the current state of the ClarionTech public website
- **Reference** for design, content, or markup analysis
- **Developing** new standalone landing pages that match the ClarionTech brand
- **Baseline** for comparison if a full website redesign is undertaken

### What This Repo Is NOT For
- Running a web server (no build/serve scripts)
- Active back-end feature development (no source code)
- Automated testing (no test framework)

### Editing the Homepage HTML Capture
Treat `AI Software Development Company _ Hire Dedicated Developers.html` as **read-only by default**. Only modify it when explicitly requested. If edits are necessary:
- Preserve the overall document structure (`<!DOCTYPE html>`, `<head>`, `<body>`)
- Preserve script and style block ordering (load order matters)
- Preserve HubSpot portal ID `3852769` — required for analytics/form tracking
- Do not alter external CDN URLs without verifying the replacement is valid

### Creating New Landing Pages
Model new pages on `accelq-landing.html`:
- Single self-contained HTML file with all CSS in `<style>` blocks
- Use the CSS variable palette and font stack documented above
- Include the ClarionTech favicon (`https://www.clariontech.com/hubfs/Favicon-1.png`)
- No tracking scripts unless explicitly requested

### No Build, Test, or Lint Commands
There are no scripts to run. The repository has:
- No `package.json`
- No `Makefile`
- No CI/CD pipeline
- No linter or formatter configuration

## AI Assistant Guidelines

1. **Do not create unnecessary files.** This is a lean archive; avoid adding boilerplate, configs, or tooling unless explicitly requested.
2. **Treat the homepage HTML capture as read-only by default.** Only modify it when the user explicitly asks.
3. **Do not attempt to run or serve the HTML.** There is no local server; files are static snapshots.
4. **Preserve external integrations.** Do not remove or alter HubSpot, Google, or other analytics scripts without explicit instruction.
5. **Follow the design conventions above** when building new landing pages to maintain visual consistency.
6. **Commit messages should be descriptive.** Since history is minimal, clear messages help track what changed and why.
7. **Push to the correct branch.** All Claude work goes to the `claude/` branch specified at session start — never directly to `master`.
