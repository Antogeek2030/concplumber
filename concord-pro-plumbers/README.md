# Concord Pro Plumbers — Water Heater Repair (Astro)

Static Astro site for **concordproplumbers.com**, optimized for Cloudflare Pages.

## Features
- Responsive, mobile-first design
- Navy + amber color theme
- OpenStreetMap embed pinpointing **2644 Richard Ave, Concord, CA 94520**
- SEO: meta tags, canonical, JSON-LD LocalBusiness schema, sitemap, robots.txt
- Markdown blog section (`src/content/blog/`)
- Fast static build for Google indexing
- Cloudflare Pages ready (static output, no adapter needed)

## Phone number
Placeholder: **(925) 555-0199** — replace across the project (search for `9255550199` and `555-0199`).

## Deploy to Cloudflare Pages
1. Push this folder to a GitHub/GitLab repo.
2. In Cloudflare Dashboard → Workers & Pages → Create → Connect to Git.
3. Build settings:
   - **Framework preset:** Astro
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
4. Add custom domain `concordproplumbers.com`.
5. Submit `https://concordproplumbers.com/sitemap-index.xml` in Google Search Console.

## Local development
```bash
npm install
npm run dev
```

## Build
```bash
npm run build
```
Output is in `dist/`.

## Blog
Add new posts as Markdown files in `src/content/blog/`. Frontmatter requires `title`, `description`, `pubDate`. Optional: `author`, `tags`, `updatedDate`.

## Notes
- Site is fully static — ideal for Cloudflare Pages and fast Google indexing.
- `@astrojs/sitemap` generates `/sitemap-index.xml` at build time.
- `public/robots.txt` points crawlers to the sitemap.
