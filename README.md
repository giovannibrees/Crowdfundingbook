# Giovanni Brees - Official Site (GitHub Pages export)

Author/book website for Giovanni Brees (giovannibreesbook.com). This folder is a
**ready-to-deploy static site** - no build step, no framework, no dependencies.

## What's in here

- `index.html` - the complete site. Fully self-contained: all images, fonts and
  CSS are inlined. This is the final production page, NOT a design reference.
  Do not rewrite or reformat it; deploy it as-is.
- `book-cover.jpg`, `book-back.jpg`, `giovanni-brees.png` - loose copies of key
  images. `index.html` does not need them to render (they're inlined), but they
  MUST exist at the site root because external crawlers fetch them by URL:
  - `og:image` / `twitter:image` -> https://www.giovannibreesbook.com/book-cover.jpg
  - JSON-LD Person image -> https://www.giovannibreesbook.com/giovanni-brees.png
- `favicon-32.png`, `favicon.png`, `apple-touch-icon.png` - favicons (also
  referenced by relative URL, so keep them at root).
- `robots.txt`, `sitemap.xml` - SEO files, must be at the site root.

## Task for Claude Code

1. Create a new GitHub repository (e.g. `giovannibrees-site`) and put every file
   in this folder at the **repo root**. Keep the flat structure - no `/docs`,
   no subfolders.
2. Enable **GitHub Pages**: Settings -> Pages -> Source: "Deploy from a branch",
   branch `main`, folder `/ (root)`.
3. Custom domain: set `www.giovannibreesbook.com` in the Pages settings (this
   creates a `CNAME` file - commit it). Enable "Enforce HTTPS" once the cert
   is issued.
4. DNS (managed at Cloudflare):
   - `CNAME` record: `www` -> `<github-username>.github.io` (DNS only /
     grey-cloud while the GitHub cert is being issued; can be proxied after).
   - Apex `giovannibreesbook.com`: A records to GitHub Pages IPs
     (185.199.108.153, .109., .110., .111.) or a Cloudflare redirect rule
     apex -> www.
5. Verify after deploy:
   - https://www.giovannibreesbook.com/ loads with HTTPS.
   - /book-cover.jpg, /giovanni-brees.png, /robots.txt, /sitemap.xml all
     resolve (200).
   - Share preview works (og:image) - test with a link preview tool.

## Do not

- Do not run a bundler, minifier or formatter over `index.html`.
- Do not move the loose assets into a subfolder (absolute URLs point at root).
- Do not add a Jekyll theme; add a `.nojekyll` file if GitHub tries to process
  the site with Jekyll.
