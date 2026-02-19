# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is the website for the Yonsei Quantum Computing Group, built with Jekyll using the `minimal-mistakes-jekyll` theme. It is deployed to GitHub Pages at `yonseiqc.github.io`.

## Commands

```bash
# Install dependencies
bundle install

# Serve locally with live reload (visit http://localhost:4000)
bundle exec jekyll serve

# Build the site to _site/
bundle exec jekyll build
```

## Architecture

- **`_config.yml`** — Site-wide settings: title, theme skin, plugins, base URL. Changes here require restarting the dev server.
- **`_posts/`** — Blog posts in Markdown, named `YYYY-MM-DD-title.markdown` with Jekyll front matter.
- **`index.markdown`** — Homepage using `layout: home` (lists recent posts).
- **`about.markdown`** — About page at `/about/`.
- **`_site/`** — Jekyll build output; do not edit directly.

## Theme

The site uses [`minimal-mistakes-jekyll`](https://mmistakes.github.io/minimal-mistakes/). The active skin is set via `minimal_mistakes_skin` in `_config.yml`. To override theme layouts or includes, create matching files under `_layouts/` or `_includes/` — Jekyll will prefer local files over the gem's defaults.

## Content Conventions

- New pages: add a Markdown file at the root with `layout: page` front matter.
- New posts: add to `_posts/` with filename `YYYY-MM-DD-slug.markdown` and include `layout: post`, `title`, `date`, and `categories` in the front matter.
