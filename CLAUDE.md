# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic website for Philippe Sloksnath, built with [Quarto](https://quarto.org/) and hosted on GitHub Pages at `philippesloksnath.com`.

## Build & Preview Commands

```bash
# Render the site (outputs to docs/)
quarto render

# Live preview with hot reload
quarto preview
```

No package manager (npm/pip) is needed. Quarto must be installed separately. All frontend dependencies (Bootstrap Icons, Academicons) are loaded via CDN.

## Architecture

**Source files** are `.qmd` (Quarto Markdown) files in the root directory. Quarto renders them to static HTML in `docs/`, which GitHub Pages serves.

Key files:
- `_quarto.yml` — site configuration (theme, navbar, sidebar, output dir)
- `styles.css` — custom CSS overrides (navbar, sidebar, profile image, responsive breakpoints)
- `index.qmd`, `research.qmd`, `blog.qmd`, `contact.qmd` — page content
- `posts/` — blog post directory (currently empty; add `.qmd` files here for blog posts)
- `assets/cv.pdf` — CV linked from sidebar
- `docs/` — build output (committed to repo for GitHub Pages)

**Theme:** Bootstrap "spacelab" with a dark pinned navbar and a docked sidebar. The sidebar contains research interests, a CV download button, and social icons.

**Blog:** `blog.qmd` is a Quarto listing page that auto-discovers posts in `posts/` sorted by date descending.

## Deployment

1. Edit `.qmd` source files
2. Run `quarto render`
3. Commit both source changes and updated `docs/` output
4. Push to `main` — GitHub Pages serves from `docs/`
