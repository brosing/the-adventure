# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this workspace is

Root workspace for **"The Boy Who Collected Silence"** — a cozy interactive-fiction project: three product surfaces plus the shared engine, four submodules total, each its own git repository with its own remote (and its own `CLAUDE.md` where applicable):

| Submodule                                     | What it is                                                                      | Stack                                                                                                        |
| --------------------------------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `md-rpg/`                                     | Headless Markdown story engine — parser + `GameEngine` state machine, no UI/platform code. Reusable across games; publishable to npm. | TypeScript, `node:test` via `tsx`                                                                              |
| `the-boy-who-collected-silence/`              | The game itself — static site + native iOS/Android via Capacitor. Consumes `md-rpg` as a pinned GitHub dependency (`package.json` → `github:brosing/md-rpg#<sha>`, transpiled via `transpilePackages`); no submodule or workspace copy inside the game repo. | Next.js 16 (static export), TypeScript, Tailwind v4, Capacitor 8 |
| `the-boy-who-collected-silence-landing-page/` | Marketing/download page                                                         | Next.js 16 (static export), Three.js particle backdrop, deployed to Cloudflare Pages/Workers via `wrangler`    |
| `the-boy-who-collected-silence-reader-view/`  | "Quiet Reader" — distraction-free reader browser extension, themed on the story | Vanilla JS, Manifest V3 (Chrome) + Safari port, no build step                                                  |

Read the submodule's own `CLAUDE.md` before working inside it — each has stack-specific commands, architecture notes, and constraints (e.g. the game repo's engine/presentation split, the landing page's design brief). This root file only covers things that span or precede all four.

`md-rpg` is intentionally tracked **twice, two different ways**: as a submodule of this root repo (orchestration/visibility — no build consumes this checkout) and as a pinned GitHub dependency in the game's `package.json` (the actual build input; `pnpm install` resolves it into `node_modules`). The game's pin is authoritative; the root submodule should follow it. When the engine changes: commit/push in `md-rpg` → bump the game's pinned SHA + `pnpm install` → sync the root submodule pointers. Full ordering and trade-offs: [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).

### Shared visual language

All three surfaces intentionally share one aesthetic: dark, late-night, `oklch`-based color themes, warm amber accents, editorial serif display type, calm/reduced-motion-respecting animation. When touching visual or copy work in any submodule, keep it consistent with the other two rather than inventing a new direction — check the landing page's design brief and the reader extension's theme palette as reference points.

## Working with the submodules

Each of the four directories above is a **separate git repository** (own remote under `github.com/brosing/...`); this root repo only stores a pinned commit (a gitlink) for each, tracked in `.gitmodules`.

- **First clone / missing submodule content**: `git clone --recurse-submodules git@github.com:brosing/the-adventure.git`, or if already cloned: `git submodule update --init --recursive`.
- **Making changes inside a submodule**: `cd` into it, commit and push there **first**, against its own `origin` — same as any standalone repo.
- **Updating the pointer at root**: after pushing inside the submodule, come back to the root repo and `git add <submodule-dir> && git commit` — this records the new commit the parent repo points to. Do this deliberately; don't let the pointer drift silently.
- `git status` at root shows a submodule as dirty only if its checked-out commit differs from the pinned one, or it has uncommitted changes — it does not expand into the submodule's own file-level diffs.
- Root-level files (this file, `README.md`, `docs/`, `.agents/`, `.claude/`) are tracked directly in this repo, not inside any submodule.

## Shared skill library

- `.agents/skills/` is the **source of truth** for this project's skill library — real directories, tracked in git. Edit skills here.
- `.claude/skills/` is a mirror of symlinks (`<name>` → `../../.agents/skills/<name>`) so Claude Code discovers the same skills. Every skill directory in `.agents/skills/` must have a matching symlink here — when you add a skill, add its symlink in the same commit.

## Crucial AI Workflow Rule

### Planning and Model Switching Stop Rule

- **Rule**: Whenever you are in **Planning Mode** and finish creating or updating the `implementation_plan.md` (or equivalent), **you must stop execution immediately**.
- **Execution Details**:
  - Do NOT ask for the user's feedback.
  - Do NOT ask what to do next.
  - Do NOT prompt the user to proceed.
  - Simply output a brief statement (e.g., "Plan is ready. Stopping for model switch.") and stop calling tools to yield your turn. This allows the user to easily switch models.

- **Rule**: Whenever you are in finish on implementing changes, never commit or create a pull request so I can review the changes.