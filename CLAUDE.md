# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this workspace is

Root workspace for **"The Boy Who Collected Silence"** — a cozy interactive-fiction project shipped across three surfaces, plus a shared engine, each its own git submodule with its own remote (and its own `CLAUDE.md` where applicable):

| Submodule                                     | What it is                                                                      | Stack                                                                                                        |
| --------------------------------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `md-rpg/`                                     | Headless Markdown story engine — parser + `GameEngine` state machine, no UI/platform code. Reusable across games; publishable to npm. | TypeScript, `node:test` via `tsx`                                                                              |
| `the-boy-who-collected-silence/`              | The game itself — static site + native iOS/Android via Capacitor. Depends on `md-rpg` as its own submodule + pnpm workspace member (`packages/md-rpg`, `workspace:*`) so it stays independently buildable/deployable. | Next.js 16 (static export), TypeScript, Tailwind v4, Capacitor 8 |
| `the-boy-who-collected-silence-landing-page/` | Marketing/download page                                                         | Next.js 16 (static export), Three.js particle backdrop, deployed to Cloudflare Pages/Workers via `wrangler`    |
| `the-boy-who-collected-silence-reader-view/`  | "Quiet Reader" — distraction-free reader browser extension, themed on the story | Vanilla JS, Manifest V3 (Chrome) + Safari port, no build step                                                  |

Read the submodule's own `CLAUDE.md` before working inside it — each has stack-specific commands, architecture notes, and constraints (e.g. the game repo's engine/presentation split, the landing page's design brief). This root file only covers things that span or precede all four.

`md-rpg` is intentionally submoduled into **both** this root repo (for orchestration/visibility across whatever games use it) **and** into `the-boy-who-collected-silence` itself (so that repo can build standalone without depending on this monorepo wrapper existing). The two checkouts are independent — keep their pinned commits in sync deliberately when the engine changes, same as any submodule update.

### Shared visual language

All three surfaces intentionally share one aesthetic: dark, late-night, `oklch`-based color themes, warm amber accents, editorial serif display type, calm/reduced-motion-respecting animation. When touching visual or copy work in any submodule, keep it consistent with the other two rather than inventing a new direction — check the landing page's design brief and the reader extension's theme palette as reference pointxss.

## Working with the submodules

Each of the three directories above is a **separate git repository** (own remote under `github.com/brosing/...`); this root repo only stores a pinned commit (a gitlink) for each, tracked in `.gitmodules`.

- **First clone / missing submodule content**: `git clone --recurse-submodules git@github.com:brosing/the-adventure.git`, or if already cloned: `git submodule update --init --recursive`.
- **Making changes inside a submodule**: `cd` into it, commit and push there **first**, against its own `origin` — same as any standalone repo.
- **Updating the pointer at root**: after pushing inside the submodule, come back to the root repo and `git add <submodule-dir> && git commit` — this records the new commit the parent repo points to. Do this deliberately; don't let the pointer drift silently.
- `git status` at root shows a submodule as dirty only if its checked-out commit differs from the pinned one, or it has uncommitted changes — it does not expand into the submodule's own file-level diffs.
- Root-level files (this file, `skills/`, `.agents/`, `.claude/`) are tracked directly in this repo, not inside any submodule.

## Shared skill library

- `skills/` is the source of truth for this project's skill library and is what's tracked meaningfully in git history.
- `.agents/skills/` and `.claude/skills/` are mirrored/symlinked copies used for agent tool discovery — an active sync process keeps them in step with `skills/`. Edit skills under `skills/`, not the mirrors directly.

## Crucial AI Workflow Rule

### Planning and Model Switching Stop Rule

- **Rule**: Whenever you are in **Planning Mode** and finish creating or updating the `implementation_plan.md` (or equivalent), **you must stop execution immediately**.
- **Execution Details**:
  - Do NOT ask for the user's feedback.
  - Do NOT ask what to do next.
  - Do NOT prompt the user to proceed.
  - Simply output a brief statement (e.g., "Plan is ready. Stopping for model switch.") and stop calling tools to yield your turn. This allows the user to easily switch models.
