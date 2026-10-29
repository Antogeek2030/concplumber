# Concord Pro Plumbers — Water Heater Repair (Astro)

Static Astro site for **concordproplumbers.com**, optimized for Cloudflare Pages.

## Features
- Responsive, mobile-first design
- Navy + amber color theme
- OpenStreetMap embed for **2644 Richard Ave, Concord, CA 94520**
- SEO: meta tags, canonical, JSON-LD LocalBusiness, sitemap, robots.txt
- Markdown blog (`src/content/blog/`)
- Fully static → fast Google indexing
- Cloudflare Pages ready

## Phone number
Placeholder: **(925) 555-0199** — search the project for `555-0199` / `9255550199` and replace.

## Cloudflare Pages (recommended)

See **[DEPLOY.md](./DEPLOY.md)** for the full guide.

Quick settings:

| Setting                 | Value            |
|-------------------------|------------------|
| Framework preset        | Astro            |
| Build command           | `npm run build`  |
| Build output directory  | `dist`           |
| Node.js version         | 22               |

## Local development

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

Output lands in `dist/`.

## Blog

Add new posts as Markdown files in `src/content/blog/`.

Required frontmatter: `title`, `description`, `pubDate`.
