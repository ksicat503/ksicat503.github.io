# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A personal portfolio and blog site for Kevin Michael Sicat, built with the [Contrast](https://github.com/niklasbuschmann/contrast) Jekyll theme and deployed to GitHub Pages at `ksicat503.github.io`.

## Local development

Requires Ruby. Install dependencies once:

```bash
gem install bundler jekyll jekyll-feed
bundle install
```

Serve locally with live reload:

```bash
bundle exec jekyll serve
```

The site is then available at `http://localhost:4000`.

## Architecture

This is a standard Jekyll site. Key files to know:

- **`_config.yml`** — all site-wide settings: title, navigation menu, external links (mail, GitHub, LinkedIn), layout flags
- **`index.md`** — homepage content
- **`projects.md`** — projects list (the only nav item currently active)
- **`_layouts/`** — `default.html` is the root shell; `page.html` and `post.html` extend it
- **`_includes/`** — partials: `head.html` (CSS/JS selection logic), `menu.html`, `sidebar.html`, `meta.html`
- **`_posts/`** — blog posts in `YYYY-MM-DD-title.md` format (currently only placeholder posts from the theme)
- **`assets/css/`** — three SASS entry points (`frame.sass`, `index.sass`, `minimal.sass`) compiled by Jekyll; which one loads is controlled by `show_frame`/`show_minimal` flags in `_config.yml`
- **`_sass/`** — shared partials imported by the CSS entry points (`utils`, `basic`, `layout`, `classes`, `rouge_*`)

### Layout flags (`_config.yml`)

| Flag | Effect |
|---|---|
| `show_frame: true` | Loads `frame.css` — grey bordered frame on wide screens |
| `show_minimal: true` | Loads `minimal.css` — stripped-down layout |
| `show_sidebar: true` | Shows sidebar instead of top header |
| `show_excerpts: true` | Shows post excerpts on homepage instead of archive list |

Currently active: `show_frame: true`, everything else `false`.

### Navigation

The `navigation` and `external` arrays in `_config.yml` drive the header menu. Each entry accepts `{file, title, url, icon, sidebaricon}`. Icons reference Font Awesome v5 icon names (bundled in `assets/fontawesome/icons.svg` — no CDN).

### Math / KaTeX

Set `mathjax: true` in a post's front matter to enable KaTeX rendering. All KaTeX assets are self-hosted under `assets/katex/`.

## Content to update

- `index.md` — bio/intro
- `projects.md` — project list
- `_config.yml` — navigation, external links, site metadata
- `Kevin Michael Sicat.pdf` — resume (linked from `index.md`)
