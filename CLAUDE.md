# CLAUDE.md — Portfolio Project Context

This file gives Claude context about the project so it can assist effectively from VS Code.
Keep it updated as the project grows.

---

## Project Description

Static personal portfolio website. Single-page (SPA-like scroll) with sections:
Hero, About, Skills, Projects, and Contact.

**Framework:** Astro v4+
**Styles:** Tailwind CSS v3+
**Language:** HTML / JS / TypeScript (optional)
**Required Node:** v18+

---

## Essential Commands

```bash
# Install dependencies (only the first time or after cloning)
npm install

# Development server with hot reload at http://localhost:4321
npm run dev

# Production build (output in /dist)
npm run build

# Preview the production build locally
npm run preview

# Check for TypeScript type errors
npm run astro check

# Add official Astro integrations
npx astro add tailwind       # Tailwind integration
npx astro add vercel         # Vercel adapter
npx astro add netlify        # Netlify adapter
npx astro add github-pages   # GitHub Pages adapter
```

---

## Key File Structure

```
src/
├── components/       # Reusable Astro components (one file per section)
│   ├── Hero.astro
│   ├── About.astro
│   ├── Skills.astro
│   ├── Projects.astro
│   └── Contact.astro
├── layouts/
│   └── Layout.astro  # Base layout: <html>, <head>, <meta>, <slot />
└── pages/
    └── index.astro   # Single page — imports and composes all components
```

---

## Code Conventions

### .astro Files

Each file has two sections separated by `---`:

```astro
---
// Frontmatter: imports, JS/TS logic, data fetching
import AnotherComponent from './AnotherComponent.astro';
const title = "Hello world";
---

<!-- HTML template with Tailwind classes -->
<section class="py-16 px-4">
  <h1 class="text-4xl font-bold">{title}</h1>
  <AnotherComponent />
</section>
```

### Tailwind CSS

- We use **utility-first**: all classes go inline in the HTML
- Do not create separate `.css` files except for global styles in `Layout.astro`
- For global styles, use the `<style is:global>` directive in `Layout.astro`
- Responsive mobile-first: `sm:`, `md:`, `lg:`, `xl:`

```astro
<!-- Responsive example -->
<div class="flex flex-col md:flex-row gap-4 p-4 md:p-8">
```

### Colors and Typography

Defined in `tailwind.config.mjs`. Extend here to add custom colors:

```js
// tailwind.config.mjs
export default {
  content: ['./src/**/*.{astro,html,js,jsx,md,mdx,svelte,ts,tsx,vue}'],
  theme: {
    extend: {
      colors: {
        primary: '#your-color',
        accent: '#your-accent',
      },
      fontFamily: {
        sans: ['Inter', 'sans-serif'],
      },
    },
  },
};
```

---

## Astro Configuration

File: `astro.config.mjs`

```js
import { defineConfig } from 'astro/config';
import tailwind from '@astrojs/tailwind';

export default defineConfig({
  integrations: [tailwind()],
  // For GitHub Pages add:
  // site: 'https://your-username.github.io',
  // base: '/presentation-page',
});
```

---

## Recommended VS Code Workflow

1. Open the project folder in VS Code
2. Install the recommended extensions (see below)
3. Run `npm run dev` in the integrated terminal
4. Edit components in `src/components/` — the browser updates automatically
5. To add a new section: create `src/components/NewSection.astro` and import it in `src/pages/index.astro`

---

## Recommended VS Code Extensions

Install from the Marketplace:

| Extension | ID | Purpose |
|---|---|---|
| Astro | `astro-build.astro-vscode` | Syntax highlighting and autocomplete for `.astro` files |
| Tailwind CSS IntelliSense | `bradlc.vscode-tailwindcss` | Tailwind class autocomplete |
| Prettier | `esbenp.prettier-vscode` | Automatic code formatting |
| ESLint | `dbaeumer.vscode-eslint` | JS/TS linting |

Tip: Create a `.vscode/extensions.json` file so VS Code suggests them automatically:

```json
{
  "recommendations": [
    "astro-build.astro-vscode",
    "bradlc.vscode-tailwindcss",
    "esbenp.prettier-vscode",
    "dbaeumer.vscode-eslint"
  ]
}
```

---

## Important Notes for Claude

- **Do not use React/JSX** in this project unless explicitly instructed
- **Components are `.astro` files**, not `.jsx` or `.tsx`
- **Do not create separate CSS files** — use Tailwind classes in the template
- **Personal content** (name, bio, projects) is hardcoded in the components for now; if the project grows it can be moved to a `src/data/` file in JSON or TS
- **The site is 100% static** — no API routes or server-side logic for now
- When adding a new section, always import and render it in `src/pages/index.astro`
