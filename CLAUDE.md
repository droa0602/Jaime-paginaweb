# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

Static Astro 7 site for Jaime Bohórquez, an electrician in Villanueva, Casanare (site content is in Spanish). It is currently a single mobile-first landing page. There are no integrations, UI frameworks, linter or test suite. Requires Node >= 22.23.4.

## Commands

- `npm install`: install dependencies
- `npx astro dev --background`: start the dev server (http://localhost:4321/Jaime-paginaweb/, because of the GitHub Pages base path) in background mode, as required by `AGENTS.md`. Manage it with `npx astro dev stop`, `npx astro dev status` and `npx astro dev logs`.
- `npm run build`: production build to `./dist/`
- `npm run preview`: serve the built site locally
- `npm run astro -- check`: type-check `.astro` files (TypeScript runs in `astro/tsconfigs/strict` mode). It needs `@astrojs/check` and `typescript`, which aren't installed yet, and prompts to install them.
- `npm run astro -- add <integration>`: add integrations such as React or Tailwind

## Architecture

- Routing is file-based: every `.astro`/`.md` file in `src/pages/` becomes a route. Put reusable components in `src/components/` and static assets (served from the site root, e.g. `/favicon.svg`) in `public/`.
- `src/layouts/Base.astro` holds the `<html>` shell (meta tags, font preloads, global CSS import). Pages pass `title` and `description` to it.
- Deployment: GitHub Pages at https://droa0602.github.io/Jaime-paginaweb/. `.github/workflows/deploy.yml` builds with `withastro/action` and publishes on every push to `main`. `astro.config.mjs` sets `site` and `base: '/Jaime-paginaweb'`, so any link to a file in `public/` or another page must include the base: use `import.meta.env.BASE_URL` (as `Base.astro` does). Vite adds the base to `url()` paths in CSS by itself.
- `src/styles/global.css` holds the design tokens (`--color-ink` #16130f for the ground, `--color-panel` #132841 dark blue for every panel and filled button, `--color-text` #e5ded2 for all text and `--color-text-soft` for secondary lines, `--color-cta` #798da6 for the floating WhatsApp button, whose text is dark blue for contrast; five type sizes `--step-*`, `--margin`, `--section`, motion easings), the flat `.btn` / `.btn-ink` / `.btn-panel` / `.btn-cta` buttons and the `[data-reveal]` scroll entrance. Page-specific styles go in each page's scoped `<style>` and should use these tokens.
- The page has two sections: the hero and the services (with the experience box — a large "30 años de oficio", then "De lunes a domingo" and "Trabajo con garantía" — beside the sheet). The client removed "Quién soy", the contact coupon, the photo band and the "Voy hasta su puerta" footer card; the footer is now only the cover photo's credit line. Contact happens through the hero card's buttons and the WhatsApp bar.
- Design concept: the page is the sticker an electrician leaves on the breaker panel door (hero card), and the services are the panel's circuit directory. All panels are dark blue, straight-edged and untilted; the services sheet keeps its content left-aligned in one column centred in the panel. The design rules come from the `design-taste-frontend` skill: no small labels above headings, no thin divider lines, no gradients, no shadows at rest. Its working files go in `.taste-skill/` (git-ignored).
- Font: Zilla Slab (400, 400 italic, 600; latin and latin-ext subsets), self-hosted in `public/fonts/` and declared in `global.css`.
- Photos live in `src/assets/fotos/` and are rendered with `astro:assets` `<Image>` (resized to WebP at build time). The only one left is the hero photo, an openly licensed picture from Wikimedia Commons (CC BY-SA 4.0) shown in greyscale; `credits.json` there and the `credit` object in the page record its source and licence, and the footer prints the credit line, which the licence requires. It doesn't show Jaime or his work.
- Page content such as the years and facts of the experience box, services and the photo credit lives in the page frontmatter. The phone number and WhatsApp link are defined there once.
- Mobile-first: base styles are the phone layout with a sticky WhatsApp bar. A single `@media (min-width: 900px)` block at the end of the page styles puts services in two columns (the pinned stub + statement, and the sheet) and turns the WhatsApp bar into a floating button. The bar hides while the hero card (which has its own WhatsApp button) is on screen.
- All motion sits inside `prefers-reduced-motion: no-preference`, so it doesn't run on a machine with animations turned off (Windows "Animation effects" off counts).

## Project docs (`docs/`)

- `docs/brief.md`: the project brief. Read it before making design or content decisions.
- `docs/decisiones.md`: why X was chosen over Y (colors, structure, tools). Add an entry whenever a choice like that is made.
- `docs/bitacora.md`: a short note added at the end of each work session (what was done, what's pending).
- `docs/plantillas/`: one template per page or entry type.
- `docs/referencias/`: reference material. `Jaime Bohorquez.html` is the original design, exported as a self-unpacking bundle (it needs JavaScript to render; its real HTML and fonts are base64/gzip inside `<script type="__bundler/...">` tags).

These docs are written in Spanish.

## Documentation

Read the relevant Astro guide at https://docs.astro.build before working on routing/middleware, components, framework components, content collections, styling/Tailwind or i18n (links are in `AGENTS.md`).
