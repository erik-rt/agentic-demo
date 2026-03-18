# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

SpendLens — a personal finance dashboard built with SvelteKit. Demo app showcasing autonomous agentic coding capabilities. See `PRD.json` for the full task breakdown.

## Commands

```bash
bun run dev          # start dev server
bun run build        # production build
bun run preview      # preview production build
bun run check        # svelte-kit sync + svelte-check (type checking)
bun run lint         # prettier + eslint
bun run format       # auto-format with prettier
bun run test         # run vitest (once test infra is set up)
```

Package manager is **bun** — use `bun add`, `bun install`, not npm/yarn.

## Feedback Loops

Run these feedback loops after each PRD task.

```bash
bun run check
bun run lint
bun run test
```

## Using libraries and SDKs

ALWAYS look up documentation for various libraries and SDKs before implementation.
When working through a PRD, at the start of each task, before you implement anything, you must look up the relevant documentation.
Use either Context7 MCP, WebFetch, WebSearch, or curl to do your lookups.

## Frontend Work

Use the /frontend-design skill for any UI-related work.

## Stack

- **SvelteKit** with `adapter-auto`, Svelte 5 runes mode
- **TypeScript** strict mode, bundler module resolution
- **Vite** as build tool
- **Tailwind CSS** for styling (dark-mode-first, zinc/neutral palette, teal accent)
- **chart.js** for data visualization
- **vitest** + `@testing-library/svelte` for tests

## Architecture

SvelteKit file-based routing under `src/routes/`. Shared code lives in `src/lib/`:

- `src/lib/data/` — mock transaction data
- `src/lib/utils/` — pure aggregation helpers
- `src/lib/components/` — Svelte 5 components (stat cards, chart, transaction list)

No backend/API — all data is client-side mock data.

## Conventions

- Svelte 5 runes syntax (`$state`, `$derived`, `$effect`, `$props`) — not legacy `let`/`export let`
- Prettier: tabs, single quotes, 100 char width
- ESLint flat config with TypeScript + Svelte support
