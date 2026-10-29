# Cloudflare Pages Deploy Guide

This is a **fully static** Astro site. No Cloudflare adapter is needed.

## Recommended Build Stack

| Setting                    | Value              |
|---------------------------|--------------------|
| Framework preset          | Astro              |
| Build command             | `npm run build`    |
| Build output directory    | `dist`             |
| Root directory            | `/` (or leave blank) |
| Node.js version           | 22 (or 20)         |

### Environment variables (optional but recommended)

In Cloudflare Pages → Settings → Environment variables (Production + Preview):

- `NODE_VERSION` = `22`

(Or rely on the included `.nvmrc` / `.node-version` files.)

## Step-by-step

1. Push this folder to a GitHub or GitLab repository.
2. Go to [Cloudflare Dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
3. Select the repository and branch (usually `main`).
4. Configure the build settings exactly as the table above.
5. Click **Save and Deploy**.
6. After the first successful deploy, go to **Custom domains** and add `concordproplumbers.com` (and `www` if desired).
7. In Google Search Console, submit:  
   `https://concordproplumbers.com/sitemap-index.xml`

## Local verification before deploying

```bash
npm install
npm run build
npx serve dist   # or npm run preview
```

The build must finish with exit code 0 and produce a `dist/` folder containing `index.html`, `sitemap-index.xml`, `robots.txt`, etc.

## Why this works well for SEO / speed

- Pure static HTML/CSS/JS → excellent Core Web Vitals
- Automatic sitemap via `@astrojs/sitemap`
- `robots.txt` already points to the sitemap
- Trailing-slash + directory format matches Cloudflare’s clean URLs

## Common issues & fixes

| Problem                         | Fix |
|---------------------------------|-----|
| Build fails on “astro not found”| Make sure `package.json` has the scripts and run `npm install` first (Cloudflare does this automatically) |
| Wrong Node version              | Set `NODE_VERSION=22` in environment variables |
| 404 on blog posts               | Ensure `trailingSlash: 'always'` and `build.format: 'directory'` stay as they are |
| Sitemap missing                 | Confirm `@astrojs/sitemap` is in dependencies and `site` is set in `astro.config.mjs` |

## Optional: Direct upload (no Git)

```bash
npm run build
npx wrangler pages deploy dist --project-name=concord-pro-plumbers
```
