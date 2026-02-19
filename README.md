# anishzute.com

Personal portfolio and blog built with [Astro 5](https://astro.build). Fully static, zero client JS by default, deployed to GitHub Pages at [anishzute.com](https://anishzute.com).

## Local Development

```sh
# Install dependencies (Node 20+ recommended)
npm install

# Start dev server at http://localhost:4321
npm run dev

# Build for production (outputs to ./dist)
npm run build

# Preview production build locally
npm run preview
```

## Project Structure

```
src/
├── content/
│   ├── config.ts              # Blog collection schema (Zod)
│   └── blog/                  # Blog posts as Markdown files
├── data/
│   ├── projects.json          # Portfolio projects
│   ├── skills.json            # Skills by category
│   └── films.json             # Filmmaking / YouTube entries
├── layouts/
│   ├── BaseLayout.astro       # Global layout with SEO/OG tags
│   └── BlogPost.astro         # Blog post layout
├── components/
│   ├── Nav.astro
│   └── Footer.astro
└── pages/
    ├── index.astro
    ├── about.astro
    ├── photography.astro
    ├── filmmaking.astro
    ├── rss.xml.js
    ├── projects/
    │   ├── index.astro
    │   └── [slug].astro
    └── blog/
        ├── index.astro
        └── [slug].astro

public/
└── images/
    └── photography/           # Drop local photo files here
```

---

## How to Add a Project

1. Open `src/data/projects.json`.
2. Add a new object to the array:

```json
{
  "slug": "my-project",
  "title": "My Project",
  "description": "One-sentence summary shown in the card.",
  "tags": ["engineering", "software"],
  "images": ["/images/projects/my-project-01.jpg"],
  "githubUrl": "https://github.com/anishzute/my-project",
  "liveUrl": null,
  "body": "Full description of the project displayed on the detail page."
}
```

3. Place any images in `public/images/projects/` and reference them as `/images/projects/your-image.jpg`.
4. The project will appear at `/projects/my-project` automatically.

---

## How to Add Photos

Photos are displayed in a masonry grid on the `/photography` page.

**Option A — Local files (recommended for production):**

1. Place your `.jpg` / `.webp` files in `public/images/photography/`.
2. Open `src/pages/photography.astro`.
3. Add entries to the `photos` array:

```ts
{
  src: '/images/photography/your-photo.jpg',
  alt: 'Descriptive alt text',
  width: 1200,   // actual pixel width of the file
  height: 800,   // actual pixel height
}
```

**Option B — External URLs:**

Use the same array format with a full URL as `src`. Useful for images already hosted elsewhere.

---

## How to Add a Blog Post

1. Create a new Markdown file in `src/content/blog/`:

```
src/content/blog/your-post-slug.md
```

2. Add the required frontmatter:

```md
---
title: "Your Post Title"
description: "A one- or two-sentence summary for the list page and RSS."
pubDate: 2025-06-01
tags: ["engineering", "motorsport"]
heroImage: "/images/blog/your-hero.jpg"   # optional
draft: false
---

Your content here...
```

3. The post appears at `/blog/your-post-slug`.
4. Set `draft: true` to hide it in production builds while keeping it visible in `npm run dev`.
5. The RSS feed at `/rss.xml` updates automatically on the next build.

**Frontmatter reference:**

| Field | Type | Required | Notes |
|---|---|---|---|
| `title` | string | yes | |
| `description` | string | yes | Used in list, RSS, and OG tags |
| `pubDate` | date | yes | `YYYY-MM-DD` |
| `updatedDate` | date | no | Shows "Updated on…" below the date |
| `tags` | string[] | no | |
| `heroImage` | string | no | URL or `/public` path; used as OG image |
| `draft` | boolean | no | Defaults to `false` |

---

## How to Add a Film

1. Open `src/data/films.json`.
2. Add an entry:

```json
{
  "title": "Your Film Title",
  "description": "Short description shown below the embed.",
  "youtubeId": "dQw4w9WgXcQ",
  "year": 2025
}
```

The video appears embedded on the `/filmmaking` page in the order listed.

---

## GitHub Pages Deployment

### One-time setup

1. Push this repo to GitHub.
2. In the repo settings, go to **Pages → Source** and select **GitHub Actions**.
3. The workflow at `.github/workflows/deploy.yml` runs automatically on every push to `main` and deploys to `https://<username>.github.io/<repo>`.

### Custom domain (anishzute.com via Cloudflare)

**GitHub side:**

1. In **Settings → Pages → Custom domain**, enter `anishzute.com` and save.  
   GitHub will add a `CNAME` file to your repo automatically.

**Cloudflare DNS:**

2. Log in to Cloudflare and select your domain.
3. Add the following DNS records (use **DNS-only / grey-cloud** — do **not** proxy through Cloudflare, as GitHub Pages handles HTTPS):

| Type | Name | Content |
|---|---|---|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `<username>.github.io` |

4. Set **Proxy status** to **DNS only** (grey cloud icon) for each record — proxying through Cloudflare conflicts with GitHub Pages' HTTPS provisioning.
5. Back in GitHub Pages settings, tick **Enforce HTTPS** once the certificate provisions (can take up to 24 hours).

> **Note on Cloudflare proxy:** If you later want to enable the Cloudflare proxy (orange cloud) for CDN/firewall benefits, set the SSL/TLS mode to **Full** in Cloudflare. But for the initial setup, DNS-only is the simplest path.
