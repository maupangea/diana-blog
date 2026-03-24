# CLAUDE.md

Guidelines for working on this project.

## Stack

- **Astro v6** — static site generator (no SSR, output is always `static`)
- **Tailwind CSS v4** — via `@tailwindcss/vite` plugin; no `tailwind.config.*` file
- **MDX** — via `@astrojs/mdx`; blog posts can be `.md` or `.mdx`
- **Astro Image** — use `import { Image } from 'astro:assets'` for all local images

## Content Collections

Config lives at `src/content.config.ts` (Astro v6 convention — not `src/content/config.ts`).
The `blog` collection uses a `glob` loader pointing at `src/content/blog/`.

Blog post frontmatter schema:
```ts
title: string
description: string
pubDate: Date   // coerced from string
heroImage?: string
```

## Key Constraints

- **Zero client-side JavaScript** — no `<script>` tags, no React/Vue/Svelte islands unless strictly necessary.
- **No backend** — static export only. The contact form posts to Formspree.
- **Styling** — Tailwind utility classes. Dark theme (bg-gray-950 base). Keep it minimal.
- **No new pages without a nav link** — all top-level pages must be linked in `BaseLayout.astro`.

## Common Tasks

**Add a blog post** — create `src/content/blog/my-post.md` with the required frontmatter.

**Add a local image** — place it in `src/assets/` and import it directly in the `.astro` file:
```astro
---
import { Image } from 'astro:assets';
import myPhoto from '../assets/my-photo.jpg';
---
<Image src={myPhoto} alt="..." />
```

**Shared layout** — all pages must use `src/layouts/BaseLayout.astro` and pass at minimum a `title` prop.

## Dev Commands

```bash
npm run dev      # start dev server at http://localhost:4321
npm run build    # production build → dist/
npm run preview  # preview dist/ locally
```
