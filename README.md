# Majid Babaeifar - Personal Blog

A minimal, fast, and SEO-friendly personal blog built with Astro and Tailwind CSS.

## Features

- **Blazing Fast** - Static site generation with Astro
- **Minimal Design** - Clean, typography-focused design inspired by modern tech blogs
- **SEO Optimized** - Meta tags, sitemap, RSS feed, and Open Graph support
- **Markdown Blog Posts** - Write posts in Markdown with frontmatter
- **Responsive** - Mobile-first design that works on all devices
- **Zero Config Deployment** - Deploy to Vercel with one click

## Tech Stack

- **Framework**: [Astro](https://astro.build/) - Static site generator
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS
- **Content**: Markdown files with frontmatter
- **Deployment**: [Vercel](https://vercel.com/) - Free hosting

## Project Structure

```
/
├── public/
│   ├── favicon.svg
│   └── robots.txt
├── src/
│   ├── content/
│   │   ├── blog/           # Blog posts (Markdown)
│   │   └── config.ts       # Content collections config
│   ├── layouts/
│   │   └── BaseLayout.astro # Base layout with header/footer
│   ├── pages/
│   │   ├── blog/
│   │   │   └── [...slug].astro # Blog post template
│   │   ├── about.astro     # About page
│   │   ├── contact.astro   # Contact page
│   │   ├── index.astro     # Home page
│   │   └── rss.xml.js      # RSS feed
│   └── styles/
│       └── global.css      # Global styles
├── astro.config.mjs        # Astro configuration
├── package.json
└── vercel.json            # Vercel deployment config
```

## Getting Started

### Prerequisites

- Node.js 18+ installed
- npm or pnpm

### Installation

1. Clone the repository:

```bash
git clone <your-repo-url>
cd me-personal-blog
```

2. Install dependencies:

```bash
npm install
```

3. Start the development server:

```bash
npm run dev
```

4. Open [http://localhost:4321](http://localhost:4321) in your browser

## Available Commands

| Command             | Action                                 |
| ------------------- | -------------------------------------- |
| `npm install`       | Install dependencies                   |
| `npm run dev`       | Start dev server at `localhost:4321`   |
| `npm run build`     | Build production site to `./dist/`     |
| `npm run preview`   | Preview build locally before deploying |
| `npm run astro ...` | Run Astro CLI commands                 |

## Writing Blog Posts

1. Create a new Markdown file in `src/content/blog/`:

```bash
src/content/blog/my-new-post.md
```

2. Add frontmatter and content:

```markdown
---
title: 'My New Post'
description: 'A brief description of my post'
pubDate: 2024-12-18
tags: ['javascript', 'web-dev']
draft: false
---

# My New Post

Your content here...
```

3. The post will automatically appear on the home page and be included in the RSS feed

## Deployment to Vercel

### Option 1: Automatic (Recommended)

1. Push your code to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Click "New Project"
4. Import your GitHub repository
5. Vercel will auto-detect Astro and deploy

### Option 2: Vercel CLI

```bash
npm install -g vercel
vercel
```

### Post-Deployment

1. Update the `site` URL in `astro.config.mjs` with your actual domain
2. Update URLs in `public/robots.txt`
3. Update social links in the footer (if needed)

## Customization

### Update Personal Information

1. **About Page**: Edit `src/pages/about.astro`
2. **Contact Info**: Edit `src/pages/contact.astro`
3. **Home Page Intro**: Edit `src/pages/index.astro`
4. **Footer Links**: Edit `src/layouts/BaseLayout.astro`

### Styling

- Global styles: `src/styles/global.css`
- Color scheme: Update CSS variables in `global.css`
- Tailwind config: Uses Tailwind v4 with `@theme` in CSS

### SEO

- Meta tags are in `src/layouts/BaseLayout.astro`
- Update `site` in `astro.config.mjs` with your domain
- Sitemap is auto-generated at `/sitemap-index.xml`
- RSS feed is at `/rss.xml`

## SEO Features

- **Meta Tags**: Title, description, Open Graph, Twitter Cards
- **Sitemap**: Auto-generated XML sitemap
- **RSS Feed**: Full RSS feed for blog posts
- **Robots.txt**: Search engine indexing configuration
- **Canonical URLs**: Prevent duplicate content issues
- **Semantic HTML**: Proper heading hierarchy and semantic tags

## Performance

- Static HTML generation (no JavaScript by default)
- Optimized images and assets
- Minimal CSS with Tailwind
- Fast page loads and excellent Core Web Vitals

## License

MIT

## Author

**Majid Babaeifar**

- Email: majidbabaeifar@gmail.com
- LinkedIn: [linkedin.com/in/majidbabaeifar](https://linkedin.com/in/majidbabaeifar)
- Location: Bamberg, Germany

---

Built with [Astro](https://astro.build/) and [Tailwind CSS](https://tailwindcss.com/)
