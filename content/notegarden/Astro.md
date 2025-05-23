---
title: Astro
draft: false
---
 

[Install Astro](https://docs.astro.build/en/install-and-setup/)

> The [`create astro` CLI command](https://docs.astro.build/en/install-and-setup/#install-from-the-cli-wizard) is the fastest way to start a new Astro project from scratch. It will walk you through every step of setting up your new Astro project and allow you to choose from a few different official starter templates.
> 
> You can also run the CLI command with the `template` flag to begin your project using any existing theme or starter template. 

[Themes and starters showcase](https://astro.build/themes/) 

***

[Tutorial: build a blog](https://docs.astro.build/en/tutorial)

- Create pages with `.astro` syntax
- Add blog posts with Markdown (`.md`) files
- Style an individual page with `<style>`
- Apply global styles across pages

The two sections of a `.astro` file work together to create a page.

> Astro uses standard HTML `<a>` elements to navigate between pages (also called _routes_), with traditional page refreshes.

***
[Migrating WordPress Blog with Flat URL Structure](https://www.reddit.com/r/astrojs/comments/1kffztz/migrating_wordpress_blog_with_flat_url_structure/)

> Create a [slug] page at the root of src/pages. Such that it is src/pages/[slug].astro
> 
> Then at the slug, load the content collection accordingly.
> 
> If you are using an astro template, move the file at src/pages/blog/[slug].astro and it should work fine.

***

To achieve flattened URLs (e.g., /best-rpgs-2025/) while saving generated HTML files inside category folders at build time (e.g., dist/news/best-rpgs-2025/index.html), you can customize your Astro setup like this:

1. Content Structure: Keep your content organized by category, e.g.: src/content/blog/news/post1.md src/content/blog/reviews/post2.md src/content/blog/guides/post3.md src/content/blog/blog/post4.md

2. Flatten URL Slugs: In your astro.config.mjs, add a custom slug function inside defineCollection: 

```
import { defineCollection, z } from 'astro:content';

const blog = defineCollection({ schema: z.object({ title: z.string(), category: z.enum(['news', 'reviews', 'guides', 'blog']), pubDate: z.string(), }), slug: ({ id, data }) => id.split('/').pop().replace(/.mdx?$/, ''), });

export const collections = { blog };
```

This keeps URLs flat: /my-post/ instead of /category/my-post/.

3. Output to Category Folders at Build: In your [slug].astro page, generate the output path based on the category manually:

```
import { getEntryBySlug } from 'astro:content'; import { Astro } from 'astro';

const { slug } = Astro.params; const entry = await getEntryBySlug('blog', slug);

if (!entry) throw new Error(`No post found for slug: ${slug}`);

## Astro.page.output = /dist/${entry.data.category}/${slug}/index.html; // <-- Custom output path

<article> <h1>{entry.data.title}</h1> <p>{entry.data.pubDate}</p> {entry.body} </article>
```

Important: Astro doesn’t support setting output paths directly in this way by default. For full control, use Astro’s build.pages hook or a custom integration/plugin.