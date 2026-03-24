**Project**: Build a personal website and blog using Astro.
**Role**: You are an expert frontend developer specializing in Astro, Jamstack, and minimal, highly-performant web architectures.

## Step 1: Initialization & Setup

- Please initialize a new Astro project in the current directory. Use whatever non-interactive commands are necessary (e.g., npm create astro@latest . -- --yes --template minimal).
- Install Tailwind CSS for styling (npx astro add tailwind --yes).
- Install MDX support (npx astro add mdx --yes).

## Step 2: Architecture & Content Collections

- Configure Astro Content Collections for the blog. Create src/content/config.ts and define a collection called blog with a schema that includes title, description, pubDate, and an optional heroImage.
- Create a sample markdown post in src/content/blog/first-post.md to ensure the routing works.

## Step 3: Build the Pages
Please create the following pages and structure:

1. Index (src/pages/index.astro): This is the Bio/Home page. Include a brief professional bio section.
2. Blog Index (src/pages/blog/index.astro): Fetch and display a list of all posts from the blog content collection, sorted by date.
3. Blog Post Routing (src/pages/blog/[...slug].astro): Set up getStaticPaths to dynamically generate individual blog post pages from the Markdown/MDX files.
4. Photography (src/pages/photography.astro): Create a responsive CSS grid gallery. Use Astro's native <Image /> component (import { Image } from 'astro:assets';). Create a placeholder local image in src/assets/ and render it a few times in the grid to demonstrate optimization.
5. Contact (src/pages/contact.astro): Build a semantic HTML contact form (Name, Email, Message, Submit). Point the <form> action attribute to https://formspree.io/f/xwvrgnyp and set method="POST".

## Step 4: Layout & Navigation

- Create a reusable base layout component (src/layouts/BaseLayout.astro) that includes a responsive <nav> linking to Home, Blog, Photography, and Contact.
- Wrap all pages in this BaseLayout.

## Constraints & Guidelines:

- Keep the Tailwind styling clean, minimal, and dark-mode friendly.
- Zero client-side JavaScript unless absolutely necessary for a UI component.
- Do not set up a backend or database. This must remain a 100% static site export.

Please execute these steps, create the files, and let me know when the local development server is ready to be started!