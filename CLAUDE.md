# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

- `pnpm dev` - Start development server
- `pnpm build` - Build for production
- `pnpm preview` - Preview production build locally

## Architecture Overview

This is an Astro-based blog system with the following key components:

### Content Management
- Blog posts are stored in `src/content/blog/` as Markdown/MDX files
- Content collections are configured in `src/content.config.ts` with schema validation
- Posts require `title`, `pubDate`, and optional `description` and `tags` frontmatter
- Info pages (like intro) are stored in `src/content/info/`

### Routing & Pages
- Main blog listing at `/` (src/pages/index.astro)
- Individual posts at `/posts/[slug]/` (src/pages/posts/[...slug]/index.astro)
- Tag-based filtering at `/tags/[tag]/` (src/pages/tags/[tag].astro)
- Automatic RSS feed generation at `/rss.xml` (src/pages/rss.xml.ts)
- Dynamic OG image generation at `/og.png` and `/posts/[slug]/og.png`

### Styling & Components
- Tailwind CSS for styling with typography plugin
- Astro components in `src/components/` for reusable UI elements
- Layout wrapper in `src/layouts/Layout.astro` handles SEO, metadata, and site structure
- React components supported via @astrojs/react integration

### Key Features
- SEO optimized with astro-seo package
- Sitemap and RSS feed generation
- Open Graph image generation using satori
- Responsive design with mobile-first approach
- Syntax highlighting for code blocks via Astro's built-in Shiki

### Global Configuration
- Site constants in `src/consts.ts` (SITE_TITLE, SITE_DESCRIPTION)
- Site URL configured in `astro.config.mjs`
- Package manager: pnpm with Node.js version managed by Volta