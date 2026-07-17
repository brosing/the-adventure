# the-adventure

Monorepo root for **_The Boy Who Collected Silence_** — a cozy interactive-fiction project shipped across four independently-deployable pieces, each its own git submodule with its own remote:

| Submodule | What it is | Stack |
| --- | --- | --- |
| [`md-rpg/`](https://github.com/brosing/md-rpg) | Headless Markdown story engine — parser + `GameEngine` state machine, no UI/platform code. Reusable across games; publishable to npm. | TypeScript |
| [`the-boy-who-collected-silence/`](https://github.com/brosing/the-boy-who-collected-silence) | The game — static site + native iOS/Android via Capacitor | Next.js 16 (static export), Tailwind v4, Capacitor 8 |
| [`the-boy-who-collected-silence-landing-page/`](https://github.com/brosing/the-boy-who-collected-silence-landing-page) | Marketing/download page | Next.js 16 (static export), Three.js, Cloudflare Pages/Workers |
| [`the-boy-who-collected-silence-reader-view/`](https://github.com/brosing/the-boy-who-collected-silence-reader-view) | "Quiet Reader" — distraction-free reader browser extension, themed on the story | Vanilla JS, Manifest V3 (Chrome) + Safari port |

`md-rpg` is tracked in two different ways: as a submodule here (cross-project visibility — not consumed by any build), and as a pinned GitHub dependency inside the game's `package.json` (`"md-rpg": "github:brosing/md-rpg#<sha>"`, resolved into `node_modules`). The game has **no** submodule or workspace copy of the engine — it stays fully buildable standalone with a plain `pnpm install`. Full rationale, release ordering, and trade-offs: [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).

## Setup

```bash
git clone --recurse-submodules git@github.com:brosing/the-adventure.git
```

Already cloned without `--recurse-submodules`?

```bash
git submodule update --init --recursive
```

Each submodule is a separate repo — `cd` in and work as you would in any standalone checkout. See [`CLAUDE.md`](CLAUDE.md) for the full submodule workflow (committing inside a submodule vs. updating the pointer here), [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) for how the pieces relate and ship, and each submodule's own `CLAUDE.md`/`README.md` for its specific setup and commands.

The engine itself lives in [`md-rpg/`](md-rpg); the game's design specs (`ENGINE_SPEC.md`, `GAME_DESIGN.md`, …) live in the game repo's `docs/`.
