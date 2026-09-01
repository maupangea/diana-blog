# personal-blog

https://mauricio-sandoval-cuenca.vercel.app/

A personal website and blog built with [Astro](https://astro.build), Tailwind CSS, and MDX. Fully static, zero client-side JavaScript, dark-mode by default.

## Pages

| Route | Description |
|---|---|
| `/` | Bio / Home |
| `/blog` | Blog index, sorted by date |
| `/blog/[slug]` | Individual blog post |
| `/photography` | Photo grid gallery |
| `/contact` | Contact form (Formspree) |

## Tech Stack

- **[Astro v6](https://astro.build)** — static site generator
- **[Tailwind CSS v4](https://tailwindcss.com)** — utility-first styling
- **[@astrojs/mdx](https://docs.astro.build/en/guides/integrations-guide/mdx/)** — MDX support for blog posts
- **[Astro Image](https://docs.astro.build/en/guides/images/)** — automatic image optimization

## Getting Started

```bash
npm install
npm run dev       # http://localhost:4321
npm run build     # output to dist/
npm run preview   # preview the build locally
```

## Adding a Blog Post

Create a new `.md` or `.mdx` file in `src/content/blog/`:

```markdown
---
title: "My Post Title"
description: "A short summary of the post."
pubDate: 2026-03-23
heroImage: ""        # optional
---

Your content here.
```

The post will automatically appear in `/blog` and get its own route at `/blog/my-post-title`.

## Project Structure

```
src/
├── assets/           # Local images (auto-optimized by Astro)
├── content/
│   └── blog/         # Markdown/MDX blog posts
├── layouts/
│   └── BaseLayout.astro
├── pages/
│   ├── index.astro
│   ├── blog/
│   │   ├── index.astro
│   │   └── [...slug].astro
│   ├── photography.astro
│   └── contact.astro
├── styles/
│   └── global.css
└── content.config.ts # Content collection schema
```

## Deployment

This is a 100% static site. Build output lands in `dist/` and can be deployed to any static host (Netlify, Vercel, GitHub Pages, Cloudflare Pages, etc.).

```bash
npm run build
# deploy the dist/ directory
```
