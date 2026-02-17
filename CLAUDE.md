# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for [awscommunitynordics.org](https://awscommunitynordics.org/) - the AWS Community Nordics collective of Nordic AWS User Groups. Built with Hugo, hosted on Netlify from the `master` branch.

## Development Commands

```bash
# Install Hugo (macOS)
brew install hugo

# Serve locally at http://localhost:1313/
hugo serve

# Build for production (output in public/)
hugo
```

Note: `hugo.toml` changes require server restart (not hot-reloaded).

## Architecture

- **Config**: `hugo.toml` at repo root
- **Layout**: Single base template at `layouts/_default/baseof.html` (Bootstrap 4.1.3 + Font Awesome 5)
- **Content templates**: `layouts/_default/single.html` and `layouts/_default/list.html`
- **404 template**: `layouts/404.html`
- **Styling**: `static/content/default.css`
- **Pages**: Markdown files in `content/` with YAML front matter (e.g., `communityday-gbg2025.md`, `usergroups.md`)
- **Homepage**: `content/_index.md`
- **Static assets**: `static/content/img/`, `static/content/speakers/`, `static/content/organizers/`
- **Vendor JS/CSS**: `static/assets/` (Bootstrap, jQuery, Popper)
- **Netlify config**: `netlify.toml` at repo root
- **Headers**: `_headers` file (Netlify headers config, at repo root)

## Page Conventions

Each page uses YAML front matter with these fields:
- `title`: Page title
- `description`: Used for OG/Twitter meta tags
- `navigation`: Highlights active nav item (`usergroups`, `communityday`, `code-of-conduct`)
- `url`: URL path (e.g., `/communityday/`)
- `image`: OG image filename relative to `content/img/` (falls back to `og-default.jpg`)

## Community Day Pages

Each annual event gets its own page file named `communityday-{city}{year}.md` with `url` pointing to either `/communityday/` (current) or `/communityday/{year}/` (past). The current/upcoming event uses `/communityday/` directly.
