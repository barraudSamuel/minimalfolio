# Repository Guidelines

This portfolio runs on Astro 5 with Tailwind 4, so contributions should mirror the lightweight, component-first approach already present in the repo.

## Project Structure & Module Organization
- Source lives in `src/`, with routed pages in `src/pages` (e.g., `src/pages/index.astro`), reusable UI in `src/components`, shared shells in `src/layouts`, design tokens and layer styles in `src/styles`, and media in `src/assets`.
- Static files (favicons, fonts) stay in `public/`; they are copied verbatim at build time.
- Production bundles land in `dist/`. Do not edit generated `dist*` archives—regenerate via `npm run build` instead.

## Build, Test, and Development Commands
- `npm install` — install dependencies after cloning or pulling.
- `npm run dev` — start the Astro dev server at `http://localhost:4321` with hot reload.
- `npm run build` — create an optimized static bundle in `dist/`.
- `npm run preview` — serve the last build locally to validate production output.
- `npm run astro -- check` — run Astro’s diagnostics (type-safe frontmatter, config validation) before opening a PR.

## Coding Style & Naming Conventions
- Follow Astro/Prettier defaults: 2-space indentation, semicolons omitted in `.astro` frontmatter, single quotes in `.ts/.js` when practical.
- Components use PascalCase filenames (`HeroBanner.astro`); route files use kebab-case to define URLs (`case-studies.astro`).
- Scope Tailwind utility classes to the block you are editing; keep class lists ordered from layout → spacing → typography for readability.

## Testing Guidelines
- No automated test suite exists yet; rely on `npm run preview` for regression checks and inspect generated HTML/CSS.
- When adding interactive behavior, include lightweight assertions (e.g., using Astro’s `test` hook or Playwright) under a new `tests/` directory and document how to run them.

## Commit & Pull Request Guidelines
- Follow the existing Conventional Commit pattern seen in history (`feat: ...`, optional scope like `feat(layout): ...`).
- Keep commits focused, reference issues in the body when relevant, and include screenshots/GIFs for visual changes.
- PRs should state what changed, how it was tested, and any follow-up work; tag reviewers familiar with the touched area (`src/components` vs. `astro.config.mjs`).
