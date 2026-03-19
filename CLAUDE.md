# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve

# Build static site
bundle exec jekyll build
```

The generated site is output to `_site/` — do not edit files there directly.

## Architecture

This is a Jekyll personal portfolio site hosted on GitHub Pages, using the `github-pages` gem and `minima` theme.

**Key configuration** (`_config.yml`):
- Collections (`projects`, `research`, `thoughts`) are stored under `_collections/` and each outputs individual pages
- The `_pages/` directory is added via `include: ["_pages"]` so those pages are processed

**Directory structure**:
- `_layouts/` — page templates: `default` (base), `post` (project/research entries with title, team, description front matter), `section` (collection index pages), `research`, `idea`
- `_includes/` — reusable partials: `head.html`, `header.html`, `footer.html`, `carousel.html`, `button.html`
- `_pages/` — static pages (`projects.md`, `research.md`, `thoughts.md`) that serve as collection index pages
- `_collections/_projects/`, `_collections/_research/`, `_collections/_thoughts/` — individual content entries
- `_data/navbar.yml` — navbar data (currently placeholder URLs)
- `assets/` — static CSS and images

**Navigation**: `_includes/header.html` auto-generates nav links by iterating `site.collections`, skipping the built-in `posts` collection. Adding a new collection in `_config.yml` automatically adds it to the nav.

**Content front matter** (for `post` layout entries):
```yaml
layout: post
title: "Entry Title"
team: Collaborator Names
skills: relevant skills
description: Short description shown in header
image: url-to-cover-image
```
