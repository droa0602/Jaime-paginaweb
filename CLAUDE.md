# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

This is a freshly scaffolded Astro 7 site (from the `minimal` starter): a single page at `src/pages/index.astro`, an empty `astro.config.mjs`, and no integrations, UI frameworks, styling setup, linter or test suite yet. Requires Node >= 22.23.4.

## Commands

- `npm install`: install dependencies
- `npx astro dev --background`: start the dev server (localhost:4321) in background mode, as required by `AGENTS.md`. Manage it with `npx astro dev stop`, `npx astro dev status` and `npx astro dev logs`.
- `npm run build`: production build to `./dist/`
- `npm run preview`: serve the built site locally
- `npm run astro -- check`: type-check `.astro` files (TypeScript runs in `astro/tsconfigs/strict` mode)
- `npm run astro -- add <integration>`: add integrations such as React or Tailwind

## Architecture

- Routing is file-based: every `.astro`/`.md` file in `src/pages/` becomes a route. Put reusable components in `src/components/` and static assets (served from the site root, e.g. `/favicon.svg`) in `public/`.
- Each page currently contains its own full `<html>` document. Once there is more than one page, factor the shared shell into a layout component.

## Project docs (`docs/`)

- `docs/brief.md`: the project brief. Read it before making design or content decisions.
- `docs/decisiones.md`: why X was chosen over Y (colors, structure, tools). Add an entry whenever a choice like that is made.
- `docs/bitacora.md`: a short note added at the end of each work session (what was done, what's pending).
- `docs/plantillas/`: one template per page or entry type.

These docs are written in Spanish.

## Documentation

Read the relevant Astro guide at https://docs.astro.build before working on routing/middleware, components, framework components, content collections, styling/Tailwind or i18n (links are in `AGENTS.md`).
