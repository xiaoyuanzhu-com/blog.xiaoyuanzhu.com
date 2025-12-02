# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # Start dev server at localhost:4321
npm run build    # Build production site to ./dist/
npm run preview  # Preview production build locally
```

## Architecture

This is an Astro blog site using the official blog starter template.

**Content System:**
- Blog posts are Markdown/MDX files in `src/content/blog/`
- Content schema defined in `src/content.config.ts` (requires: title, description, pubDate; optional: updatedDate, heroImage)
- Posts are accessed via Astro's `getCollection('blog')` API

**Page Routing:**
- `src/pages/` uses file-based routing
- `src/pages/blog/[...slug].astro` generates dynamic blog post pages
- Static site generation via `getStaticPaths()`

**Key Files:**
- `src/consts.ts` - Global site constants (SITE_TITLE, SITE_DESCRIPTION)
- `src/layouts/BlogPost.astro` - Blog post layout wrapper
- `src/components/BaseHead.astro` - SEO meta tags and common head elements

**Integrations:**
- MDX support for enhanced Markdown
- Sitemap generation
- Sharp for image optimization
