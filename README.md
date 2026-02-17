# awscommunitynordics.org

This is the repository of the website [awscommunitynordics.org](https://awscommunitynordics.org/).

It is built with [Hugo](https://gohugo.io/) and hosted on [Netlify](https://www.netlify.com/). Pushing to the `master` branch triggers an automatic deploy.

## Branches

- **`master`** -- Production. Pushing here deploys the live site immediately. Use for small, safe content changes.
- **`develop`** -- Staging. Use for larger changes such as layout updates, template changes, new features, or anything you want reviewed before going live. When ready, open a pull request from `develop` to `master`.

## Making content changes directly on GitHub

You don't need to install anything locally for small content changes like updating event details, fixing typos, or adding speakers. You can edit files directly on GitHub:

1. Navigate to the file you want to edit in the `content/` folder
2. Click the pencil icon (Edit this file) in the top right
3. Make your changes
4. Scroll down, write a commit message, and commit directly to `master` (or create a branch and open a pull request if you prefer a review)

Netlify will automatically build and deploy your changes within a couple of minutes.

For larger changes (templates, layouts, configuration, CSS), commit to the `develop` branch instead and open a pull request to `master` when ready.

### Where to find content files

All site pages live as Markdown files in the `content/` directory:

| File | Page | URL |
|------|------|-----|
| `content/_index.md` | Homepage | `/` |
| `content/usergroups.md` | User Groups | `/usergroups/` |
| `content/communityday-gbg2025.md` | Current Community Day | `/communityday/` |
| `content/communityday-dk2024.md` | Past Community Day (DK 2024) | `/communityday/2024/` |
| `content/code-of-conduct.md` | Code of Conduct | `/code-of-conduct/` |
| `content/speaker-info.md` | Speaker Info | `/speakers/` |
| `content/sponsor-info.md` | Sponsor Info | `/sponsors/` |
| `content/gameday2024.md` | GameDay 2024 | `/gameday2024/` |

### Front matter

Every content file starts with a YAML front matter block between `---` markers. These fields control how the page appears:

```yaml
---
title: "AWS Community Day Nordics in Gothenburg 2025"
description: "Used for social media previews (OG/Twitter meta tags)"
navigation: "communityday"   # Highlights the active nav item (usergroups, communityday, code-of-conduct)
url: /communityday/          # The URL path for this page
image: "og-communityday.png" # Social sharing image (relative to static/content/img/)
---
```

### Adding a new Community Day page

Each annual event gets its own file named `communityday-{city}{year}.md`:

1. Copy an existing Community Day file (e.g., `communityday-gbg2025.md`)
2. Rename it to match the new city and year
3. Update the front matter (`title`, `description`, `url`)
4. The current/upcoming event should use `url: /communityday/`
5. Move the previous event to `url: /communityday/{year}/`
6. Update the homepage (`_index.md`) to link to the new event

### Adding images

Upload images (speaker photos, sponsor logos, etc.) to the appropriate folder under `static/`:

- Sponsor/event logos: `static/content/img/`
- Speaker photos: `static/content/speakers/{year}/`
- Organizer photos: `static/content/organizers/`

Reference them in content using paths relative to the site root, e.g.:

```html
<img src="/content/img/sponsor_logo.png" />
<img src="/content/speakers/2024/speaker_name.jpg" />
```

## Running locally

For larger changes, it's recommended to preview locally before pushing.

### Prerequisites

Install Hugo. On macOS:

```
brew install hugo
```

For other platforms, see the [Hugo installation docs](https://gohugo.io/installation/).

### Preview the site

```
hugo serve
```

Then visit [http://localhost:1313/](http://localhost:1313/). Changes to content files are hot-reloaded automatically. Changes to `hugo.toml` require a server restart.

### Build for production

```
hugo
```

Output is generated in the `public/` directory.

## Project structure

```
.
├── content/          # Markdown content pages (this is where most editing happens)
├── layouts/          # Hugo HTML templates
│   ├── _default/     # Base and default templates (baseof.html, single.html, list.html)
│   └── 404.html      # Custom 404 page
├── static/           # Static assets (copied as-is to the built site)
│   ├── assets/       # Vendored JS/CSS (Bootstrap 4.1.3, jQuery, Popper)
│   └── content/      # Site CSS, images, speaker photos, organizer photos
├── hugo.toml         # Hugo configuration
└── netlify.toml      # Netlify build configuration
```
