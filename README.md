# Giovanni Brees — Official Book Website

The official website of **Giovanni Brees** — founder, entrepreneur and author of
***The Crowdfunding Quick-Guide***.

**Live site:** [www.giovannibreesbook.com](https://www.giovannibreesbook.com)

## About

This repository hosts the production website, served with GitHub Pages. It is a
single, fully self-contained static page: all styles, fonts and imagery are
inlined in `index.html`, so there is no build step, no framework and no
dependencies — what you see in this repo is exactly what ships.

## Repository layout

| File | Purpose |
| --- | --- |
| `index.html` | The complete site (self-contained; do not minify or reformat) |
| `book-cover.jpg`, `book-back.jpg` | Book imagery, fetched by social crawlers (`og:image`) |
| `giovanni-brees.png` | Author portrait, referenced by structured data (JSON-LD) |
| `favicon-32.png`, `favicon.png`, `apple-touch-icon.png` | Favicons |
| `robots.txt`, `sitemap.xml` | SEO files |
| `CNAME` | Custom domain for GitHub Pages |

All assets intentionally live at the repository root — external crawlers fetch
them by absolute URL (e.g. `https://www.giovannibreesbook.com/book-cover.jpg`),
so they must not be moved into subfolders.

## Deployment

Pushing to the `gh-pages` branch publishes the site via GitHub Pages at the
custom domain above. `main` mirrors `gh-pages`; keep the two branches in sync
when updating the site.

---

© Giovanni Brees. All rights reserved.
