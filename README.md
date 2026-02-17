# awscommunitynordics.org

This is the repository of the website [awscommunitynordics.org](https://awscommunitynordics.org/).

It is hosted directly from this repository on Netlify.

# Running development environment locally

If you are developing major changes, it makes sense to test and validate the changes locally using Hugo. If you are doing small changes, like fixing a typo, those can be done directly to the repository with no need to install anything locally, though it is highly advisable, so you won't break anything in production.

## Installation

### Prerequisites

Install Hugo. On macOS:

```
brew install hugo
```

For other platforms, see the [Hugo installation docs](https://gohugo.io/installation/).

## Serve

To preview the site locally:

```
hugo serve
```

Then visit [http://localhost:1313/](http://localhost:1313/).

## Build

To build the site for production:

```
hugo
```

Output is generated in the `public/` directory.

## Project structure

```
.
├── content/          # Markdown content pages
├── layouts/          # Hugo templates
│   ├── _default/     # Base and default templates
│   └── 404.html      # Custom 404 page
├── static/           # Static assets (CSS, JS, images)
│   ├── assets/       # Vendored JS/CSS (Bootstrap, jQuery)
│   └── content/      # Site CSS, images, speakers, organizers
├── hugo.toml         # Hugo configuration
└── netlify.toml      # Netlify build configuration
```
