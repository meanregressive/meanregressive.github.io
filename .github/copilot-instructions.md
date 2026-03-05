# Copilot Instructions — meanregressive.github.io

## Project overview

Personal academic portfolio and essay site for Deboleena Rakshit, a Development Economist and Research Analyst II at IFPRI. Built with Jekyll, deployed on GitHub Pages. The site is intentionally minimal and typography-forward — no JavaScript frameworks, no theme dependencies, just custom SCSS and Jekyll templating.

## Owner background

- **Current role**: Research Analyst II, International Food Policy Research Institute (IFPRI), Washington DC (2023–present)
- **Research focus**: gender equality, women's economic empowerment (WEE), intimate partner violence (IPV) and transfers, household resilience, social protection programs, gender attitudes and masculinities — primarily in sub-Saharan Africa and South Asia
- **Methods**: RCT design and analysis, large-scale administrative data (Stata, Python), systematic reviews, cross-country survey harmonization
- **Intellectual arc**: B.A. English Literature (Jadavpur University, 2011) → M.A. International Relations / Development Economics (SAIS, Johns Hopkins, 2019) → math coursework for PhD preparation (Linear Algebra, Multivariable Calculus, Real Analysis, American University, 2023–2025)
- **Tools**: Stata, Python, Google Earth Engine, LaTeX, Tableau, SurveyCTO, Kobo Toolbox
- **Languages**: Bengali, English, French, Hindi

## Tech stack

- **Generator**: Jekyll (github-pages gem — pins all dependency versions to match GitHub Pages exactly)
- **Hosting**: GitHub Pages, auto-built from `main` branch
- **CSS**: Custom SCSS, no theme. All styles in `_sass/` with a central design token file (`_variables.scss`)
- **Fonts**: EB Garamond (serif body), Inter (sans-serif UI) — loaded from Google Fonts
- **No JavaScript frameworks** — the only JS is a small mobile nav toggle in `_layouts/default.html`
- **No CMS** — content is edited directly in Markdown and YAML files

## Repository structure

```
_config.yml           # site metadata, plugins, SASS config, pagination
Gemfile               # github-pages gem only
.gitignore

_layouts/
  default.html        # root shell: head + header + nav + main + footer
  home.html           # wraps index.md
  page.html           # standard content pages
  post.html           # blog essay layout
  publications.html   # adds W/J/R badge legend above content

_includes/
  head.html           # <head> with meta, Google Fonts, jekyll-seo-tag
  header.html         # site name + tagline
  nav.html            # sticky nav driven by _data/nav.yml
  footer.html         # social links + copyright
  social-links.html   # email, GitHub, LinkedIn, Twitter, Bluesky
  pub-entry.html      # reusable publication list item (used in publications.md and cv.md)

_data/
  nav.yml             # navigation items (title + url)
  publications.yml    # all publications — single source of truth, typed W/J/R
  experience.yml      # work experience — single source of truth

_sass/
  _variables.scss     # ALL design tokens: colors, fonts, spacing, radii
  _base.scss          # resets, body, container utility, code
  _typography.scss    # headings, links, blockquotes, .section-rule
  _layout.scss        # page/article wrappers, education table, pills, experience
                      # timeline, download button, tools grid, research interests,
                      # presentations
  _nav.scss           # site header, sticky nav, mobile hamburger
  _home.scss          # home page hero and section styles
  _publications.scss  # pub list, badges, pub-entry component
  _blog.scss          # blog listing, post page, pagination, tags

assets/
  css/main.scss       # imports all _sass partials (Jekyll compiles this)
  files/
    Rakshit_Deboleena_CV_2026.pdf   # linked from cv.md download button
  images/             # profile photo goes here when available

_posts/               # blog essays — filename: YYYY-MM-DD-slug.md

index.md              # home page (layout: home)
about.md              # intellectual arc narrative, education, languages, tools
research.md           # research interests, methods, work experience, presentations
publications.md       # full publications list (layout: publications)
cv.md                 # download button + web summary pulled from _data/
blog.md               # essay listing with pagination (permalink: /blog/)
```

## Design system

All tokens are CSS custom properties defined in `_sass/_variables.scss`:

| Token | Value | Use |
|---|---|---|
| `--color-bg` | `#faf9f7` | warm off-white page background |
| `--color-text` | `#1a1916` | near-black body text |
| `--color-text-muted` | `#6b6760` | dates, meta, secondary text |
| `--color-accent` | `#2c4a6e` | muted navy — matches LaTeX CV darkblue |
| `--color-border` | `#ddd9d2` | rule lines, table borders |
| `--font-serif` | EB Garamond, Palatino, Georgia | body text, headings |
| `--font-sans` | Inter, Helvetica Neue, Arial | nav, labels, meta, UI |
| `--font-size-base` | `1.125rem` (18px) | generous for long-form reading |
| `--line-height-body` | `1.75` | air for serif text |
| `--container-max` | `720px` | narrow reading column |

Publication badge colors: W (working paper) = navy `#3d5a80`, J (journal article) = green `#5a7a4a`, R (report) = terracotta `#7a5a3a`.

## Content data conventions

### `_data/publications.yml`

Each entry has these fields:
```yaml
- id: W1          # unique id (W=working paper, J=journal, R=report + number)
  type: W         # W, J, or R — drives badge color and grouping
  year: 2025
  authors: "Last, F.; Last, F."
  title: "Title of the work"
  venue: "Journal or publisher name"
  url: "https://..."   # optional DOI or handle
  note: "..."          # optional e.g. "Under review"
```

### `_data/experience.yml`

```yaml
- org: "Organization name"
  location: "City, Country"
  role: "Job title"
  dates: "YYYY–YYYY"
  bullets:
    - "Bullet point one."
    - "Bullet point two."
```

### Blog posts (`_posts/`)

Filename: `YYYY-MM-DD-slug-with-dashes.md`

```yaml
---
layout: post
title: "Essay title"
date: YYYY-MM-DD
description: "One sentence shown in listings and used for SEO meta description."
categories: [gender]          # exactly one from canonical list below
tags: [tag1, tag2]            # free-form, lowercase, hyphenated
excerpt_separator: <!--more-->
---

Opening paragraphs shown in blog listing.

<!--more-->

Rest of the essay.
```

**Canonical category slugs** (use only these):
- `gender` — gender equality, feminist theory, gender norms
- `wee` — women's economic empowerment
- `violence` — IPV, GBV, violence prevention
- `social-protection` — cash transfers, livelihoods, graduation programs
- `methods` — econometrics, research design, fieldwork, data
- `africa` — sub-Saharan Africa region
- `south-asia` — South Asia region
- `math` — reflections on quantitative training (Real Analysis, Calculus, etc.)

## Workflows

### Making changes locally

```bash
bundle install                              # first time only
bundle exec jekyll serve --livereload       # → http://localhost:4000
```

Edit files, see changes live. When done:

```bash
git add <changed files>
git commit -m "brief description"
git push
```

GitHub Pages rebuilds automatically on every push to `main`. Check the **Actions** tab for build status.

### Adding a new essay

1. Create `_posts/YYYY-MM-DD-slug.md` with the front matter above
2. Write in Markdown — use `<!--more-->` after the opening paragraphs
3. Commit and push — the Essays page updates automatically

### Adding/updating a publication

Edit `_data/publications.yml`. The change appears on both the Publications page and the CV page (which pulls the first 5 entries as "Selected Publications").

### Updating work experience

Edit `_data/experience.yml`. The change appears on both the Research page and the CV page.

### Updating the CV PDF

Replace `assets/files/Rakshit_Deboleena_CV_2026.pdf` with the new file. If the filename changes, update the `href` in `cv.md` line 8.

### Publishing / unpublishing the site

- **Unpublish**: GitHub → Settings → Pages → "Unpublish site"
- **Republish**: GitHub → Settings → Pages → Source → "Deploy from a branch" → `main` / `(root)` → Save

## Key design decisions

- **Data-driven**: Publications and experience live in `_data/` YAML, not hardcoded in page files. This ensures the Publications page, CV page, and home page recent-work strip never drift out of sync.
- **No theme dependency**: All CSS is custom. Changes to visual design never require fighting a theme's overrides.
- **Narrow reading column** (720px max): Academic convention, optimizes for long-form reading.
- **EB Garamond**: Chosen to echo the Palatino used in the LaTeX CV, maintaining visual continuity between web and PDF versions.
- **`math` category on blog**: Reserved for posts about learning Real Analysis and Calculus as part of PhD preparation — a distinctive and personal thread.
