# the-adventure

Monorepo root for **_The Boy Who Collected Silence_** — a cozy interactive-fiction project shipped across four independently-deployable pieces, each its own git submodule with its own remote:

| Submodule | What it is | Stack |
| --- | --- | --- |
| [`md-rpg/`](https://github.com/brosing/md-rpg) | Headless Markdown story engine — parser + `GameEngine` state machine, no UI/platform code. Reusable across games; publishable to npm. | TypeScript |
| [`the-boy-who-collected-silence/`](https://github.com/brosing/the-boy-who-collected-silence) | The game — static site + native iOS/Android via Capacitor | Next.js 16 (static export), Tailwind v4, Capacitor 8 |
| [`the-boy-who-collected-silence-landing-page/`](https://github.com/brosing/the-boy-who-collected-silence-landing-page) | Marketing/download page | Next.js 16 (static export), Three.js, Cloudflare Pages/Workers |
| [`the-boy-who-collected-silence-reader-view/`](https://github.com/brosing/the-boy-who-collected-silence-reader-view) | "Quiet Reader" — distraction-free reader browser extension, themed on the story | Vanilla JS, Manifest V3 (Chrome) + Safari port |

`md-rpg` is submoduled in twice: here, and inside `the-boy-who-collected-silence/packages/md-rpg` — the game keeps its own copy so it stays fully buildable on its own, without depending on this monorepo wrapper.

## Setup

```bash
git clone --recurse-submodules git@github.com:brosing/the-adventure.git
```

Already cloned without `--recurse-submodules`?

```bash
git submodule update --init --recursive
```

Each submodule is a separate repo — `cd` in and work as you would in any standalone checkout. See [`CLAUDE.md`](CLAUDE.md) for the full submodule workflow (committing inside a submodule vs. updating the pointer here) and each submodule's own `CLAUDE.md`/`README.md` for its specific setup and commands.

The engine itself (code + specs) lives in [`packages/md-rpg`](md-rpg).
