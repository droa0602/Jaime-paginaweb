# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

Static Astro 7 site for Jaime Bohórquez, an electrician in Villanueva, Casanare (site content is in Spanish). It is currently a single mobile-first landing page. There are no integrations, UI frameworks, linter or test suite. Requires Node >= 22.23.4.

## Commands

- `npm install`: install dependencies
- `npx astro dev --background`: start the dev server (localhost:4321) in background mode, as required by `AGENTS.md`. Manage it with `npx astro dev stop`, `npx astro dev status` and `npx astro dev logs`.
- `npm run build`: production build to `./dist/`
- `npm run preview`: serve the built site locally
- `npm run astro -- check`: type-check `.astro` files (TypeScript runs in `astro/tsconfigs/strict` mode). It needs `@astrojs/check` and `typescript`, which aren't installed yet, and prompts to install them.
- `npm run astro -- add <integration>`: add integrations such as React or Tailwind

## Architecture

- Routing is file-based: every `.astro`/`.md` file in `src/pages/` becomes a route. Put reusable components in `src/components/` and static assets (served from the site root, e.g. `/favicon.svg`) in `public/`.
- `src/layouts/Base.astro` holds the `<html>` shell (meta tags, font preloads, global CSS import). Pages pass `title` and `description` to it.
- `src/styles/global.css` holds the design tokens (`--color-*`, `--font-*`, `--space-*`) and the shared classes from the original "Industry" design system: `.btn`, `.blueprint` frames with `.corner` marks, `.duotone`, `.kicker`. Page-specific styles go in each page's scoped `<style>` and should use these tokens.
- Fonts (Barlow 400/700, Barlow Condensed 600; latin and latin-ext subsets) are self-hosted in `public/fonts/` and declared in `global.css`.
- Page content such as stats and services lives in arrays in the page frontmatter. The phone number and WhatsApp link are defined there once.
- The design targets a 480px-wide phone column (`.page`) with a sticky WhatsApp button at the bottom.

## Project docs (`docs/`)

- `docs/brief.md`: the project brief. Read it before making design or content decisions.
- `docs/decisiones.md`: why X was chosen over Y (colors, structure, tools). Add an entry whenever a choice like that is made.
- `docs/bitacora.md`: a short note added at the end of each work session (what was done, what's pending).
- `docs/plantillas/`: one template per page or entry type.
- `docs/referencias/`: reference material. `Jaime Bohorquez.html` is the original design, exported as a self-unpacking bundle (it needs JavaScript to render; its real HTML and fonts are base64/gzip inside `<script type="__bundler/...">` tags).

These docs are written in Spanish.

## Documentation

Read the relevant Astro guide at https://docs.astro.build before working on routing/middleware, components, framework components, content collections, styling/Tailwind or i18n (links are in `AGENTS.md`).
