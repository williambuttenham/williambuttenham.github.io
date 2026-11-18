# CLAUDE.md

Personal site of William Buttenham (www.williambuttenham.com). Hugo static site
built on a **vendored copy of the hugo-theme-gruvbox theme** — the theme's
layouts/assets live directly in this repo (not in `themes/`), so `package.json`,
`go.mod`, `theme.toml` and `gruvbox-readme.md` still carry upstream theme metadata.

## Where things are

| Path | What |
| --- | --- |
| `content/blog/<slug>/index.md` | Blog posts (page bundles; images sit beside `index.md`) |
| `content/now.md`, `about.md`, `cv.md` | Standalone pages (`cv.md` uses `type: "cv"` → `layouts/cv/single.html`) |
| `data/json_resume/en.json` | CV data (JSON Resume, via hugo-mod-json-resume) |
| `config/_default/hugo.toml` | Site config: title, params, menus, Prism languages/plugins, social share |
| `config/_default/module.toml` | Hugo module imports + mounts of `node_modules` (icons, prism, fonts) |
| `config/production/hugo.toml` | Production `baseURL` only |
| `layouts/` | Templates (`_default/`, `partials/`, `shortcodes/`, render hooks in `_default/_markup/`) |
| `assets/css/critical/`, `assets/css/non-critical/` | CSS, concatenated in numeric filename order |
| `assets/js/` | `dark-mode.js`, `flexsearch.js`, `prism.js` |
| `archetypes/default.md` | New-post front matter template |
| `.github/workflows/hugo.yml` | Deploy to GitHub Pages on push to `main` (Hugo extended 0.170.1, Node 24) |

## Do not read / edit

- `public/` — stale build output. It is gitignored but still tracked from old
  commits; CI builds its own. Never edit it or use it as a source of truth.
- `package-lock.json` (~380 KB), `node_modules/`, `resources/_gen/`, `hugo_stats.json`.
- Image files (`*.jpg`, `*.JPG`, `*.png`, `*.webp`, `*.mp4`).
- `gruvbox-readme.md` — upstream theme docs; grep it for a specific feature
  (e.g. image optimization, Prism, colors) instead of reading it whole.

## Blog post front matter

```yaml
---
title: "Post Title"
date: "2024-01-31"
description: "One-sentence summary shown in lists/SEO."
draft: false
cover:
  src: ./feature.jpg   # file in the same bundle
  caption: Optional caption
---
```

Optional keys from the archetype: `comments`, `socialShare`, `toc`, `tags`,
`categories`, `series`. Images in posts: `![alt](file.jpg "Title")` — the
render hook in `layouts/_default/_markup/render-image.html` resizes them.

## Commands

Hugo is not preinstalled in cloud sessions; only install it if a build check is
actually needed.

```bash
npm ci                         # needed before any hugo build (module mounts use node_modules)
hugo server -D                 # local dev with drafts
hugo --minify                  # production-like build (HUGO_ENVIRONMENT=production for real baseURL)
hugo new blog/<slug>/index.md  # new post from archetype
```

Linting runs via husky + lint-staged on commit: stylelint (`*.css`), eslint
(`*.js`), markdownlint with MD013 disabled (`*.md`). Prettier uses
`prettier-plugin-go-template` for `*.html` and `proseWrap: always`.
Indent: 2 spaces, LF.

## Conventions

- Content-only changes (posts, now page) touch only `content/` — no need to look
  at layouts or config.
- Menu items are in `[menu]` of `config/_default/hugo.toml` (Projects/CV/About
  are commented out on purpose).
- Copyright year string is `copyright` in `config/_default/hugo.toml`.
- Add Prism languages to `params.prism.languages` when posting code in a new language.
