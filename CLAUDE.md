# CLAUDE.md

## Project Overview

**Carbon Lab** is a static marketing website for an AI fintech product suite — "AI Side-Kicks" for finance teams. The site is hosted on GitHub Pages at [carbon-lab.io](https://carbon-lab.io).

The core value proposition: AI assistants that learn from user feedback and continuous corrections, designed for revenue accounting, fraud detection, invoicing, tax, and variance analysis workflows.

## Repository Structure

```
carbon-lab/
├── index.html                  # Main landing page
├── our-approach.html           # Company philosophy / approach page
├── pricing.html                # Pricing page
├── pilot.html                  # Early access signup form
├── sidekick-dashboard.html     # Dashboard mockup page
├── CNAME                       # GitHub Pages custom domain (carbon-lab.io)
├── README.md                   # Minimal project description
│
├── revenue-accountant/
│   └── index.html              # Contract Wizard — LIVE interactive demo
├── fraud-detection/
│   └── index.html              # Fraud Fighter — LIVE interactive demo
├── invoice-magic/
│   └── index.html              # Invoice Magic — Coming Soon placeholder
├── revenue-mapper/
│   └── index.html              # Revenue Mapper — Coming Soon placeholder
├── tax-navigator/
│   └── index.html              # Tax Navigator — Coming Soon placeholder
└── variance-detective/
    └── index.html              # Variance Detective — Coming Soon placeholder
```

## Tech Stack

- **Pure HTML/CSS/JS** — no framework, no build step, no bundler
- **Tailwind CSS** via CDN (`<script src="https://cdn.tailwindcss.com"></script>`)
- **Google Fonts** via CDN (Inter, Syne, Space Grotesk)
- **No package.json**, no npm/yarn/pnpm dependencies
- **No server-side code** — entirely client-side static files

## Development Workflow

### Running Locally

No build step required. Open any HTML file directly in a browser, or use a simple HTTP server:

```bash
python3 -m http.server 8000
# Then visit http://localhost:8000
```

### Deploying

The site is deployed via **GitHub Pages**. Pushing to the default branch (`master`) automatically deploys. The `CNAME` file maps the custom domain `carbon-lab.io`.

### No Build / No Tests / No Linting

There is no build system, test suite, or linter configured. All styling is done through Tailwind utility classes and inline `<style>` blocks within each HTML file.

## Design System & Branding

### Color Palette

| Token | Value | Usage |
|-------|-------|-------|
| `--color-carbon-orange` | `#d97342` | Primary brand color |
| `--color-carbon-orange-hover` | `#c2613a` | Hover state |
| `--color-carbon-orange-light` | `#e88b5e` | Light accent |
| `--color-carbon-orange-dark` | `#b85533` | Dark accent |

These are defined as CSS custom properties in `:root` within each page's `<style>` block.

### Typography

| Font | Role |
|------|------|
| **Inter** | Body text (clean, neutral sans-serif) |
| **Syne** | Headings (geometric, reflects crystalline carbon motif) |
| **Space Grotesk** | Logo and technical/special elements |

### Visual Motifs

- **Hexagonal patterns** (`.carbon-pattern`) — references carbon's crystalline structure
- **Molecular bond decorations** (`.carbon-bond`) — CSS pseudo-elements
- **Crystalline text shimmer** (`.carbon-crystal`) — animated gradient effect
- **Dark theme** with gradient backgrounds and backdrop blur cards

### Reusable CSS Classes

- `.carbon-logo` — Hexagon-shaped logo element
- `.carbon-pattern` — Background hexagonal grid pattern
- `.carbon-orange`, `.text-carbon-orange` — Brand color utilities
- `.bg-carbon-orange-hover`, `.shadow-carbon-orange` — Interactive states

## Page Conventions

### HTML Structure

Every page follows this pattern:

1. `<!DOCTYPE html>` with viewport meta, Google Fonts imports, Tailwind CDN
2. `<style>` block with CSS custom properties and page-specific styles
3. `<header>` with sticky navigation, logo, nav links, and CTA button
4. Semantic `<section>` elements for content
5. Tailwind utility classes for layout; custom classes for branding

### Navigation

- Sticky header across all pages
- Sub-pages include a back link (`< Carbon Lab`) to the main site
- CTA button links to `/pilot.html` (early access signup)

### Responsive Breakpoints

Standard Tailwind breakpoints: `md:` and `lg:` prefixes for responsive layouts.

## Product Pages

| Product | Directory | Status | Description |
|---------|-----------|--------|-------------|
| Contract Wizard | `/revenue-accountant/` | Live demo | ASC 606 revenue accounting training |
| Fraud Fighter | `/fraud-detection/` | Live demo | Fraud detection pattern training |
| Invoice Magic | `/invoice-magic/` | Coming Soon | Invoice processing automation |
| Revenue Mapper | `/revenue-mapper/` | Coming Soon | Revenue mapping workflows |
| Tax Navigator | `/tax-navigator/` | Coming Soon | Tax compliance assistance |
| Variance Detective | `/variance-detective/` | Coming Soon | Financial variance analysis |

Live demo pages use step-based progress indicators (`step-active` / `step-inactive` classes) with fade-in and slide-up animations.

## Conventions for AI Assistants

- **No build step** — changes to HTML files are immediately reflected when served
- **Styles are inline** — each HTML file contains its own `<style>` block; there are no shared CSS files
- **Keep CDN dependencies** — do not replace the Tailwind CDN or Google Fonts CDN with local copies
- **Maintain branding consistency** — use the documented color palette, fonts, and visual motifs
- **Follow existing page structure** — match the header/section/footer pattern of existing pages
- **Coming Soon pages share a template** — the four placeholder pages (`invoice-magic`, `revenue-mapper`, `tax-navigator`, `variance-detective`) use nearly identical markup
- **Default branch is `master`** (not `main`)
