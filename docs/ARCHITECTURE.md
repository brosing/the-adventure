# How the pieces fit together

The canonical reference for how the four repos in this workspace relate, ship, and
stay in sync. Repo-specific commands and constraints live in each submodule's own
`CLAUDE.md`/`README.md`; this doc only covers what spans them.

## The four pieces & how they talk

```
md-rpg  (public engine repo)
   │
   │  pinned GitHub dependency
   │  package.json: "md-rpg": "github:brosing/md-rpg#<sha>"
   ▼
the-boy-who-collected-silence  (the game: static site + iOS/Android)

the-boy-who-collected-silence-landing-page   (marketing site)
the-boy-who-collected-silence-reader-view    (browser extension)
```

- **md-rpg → game** is the only code dependency, and it's build-time only: `pnpm
install` fetches the engine's raw TypeScript from GitHub into `node_modules`,
  and Next transpiles it via `transpilePackages`.
- **Landing page and reader extension have no code dependency** on the engine, the
  game, or each other. What they share is the visual language — dark, late-night,
  `oklch`-based themes, warm amber accents, editorial serif display type,
  reduced-motion-respecting animation. When touching visuals or copy in any
  surface, match the other two; the landing page's design brief and the reader
  extension's theme palettes are the reference points.
- **md-rpg is the only public repo.** Its docs must stand alone: no links into the
  private repos, no references to this workspace's layout. If engine documentation
  needs game context, describe it generically ("the host game", "the original
  game") or inline the needed content.

## Dual tracking of md-rpg

The engine is tracked twice, two different ways, on purpose:

| Where                  | Form                               | Role                                                                                                                                        |
| ---------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `the-adventure/md-rpg` | git submodule (gitlink)            | Visibility/orchestration only — lets this workspace see and browse the engine alongside its consumers. **No build consumes this checkout.** |
| game's `package.json`  | `github:brosing/md-rpg#<full-sha>` | The authoritative build input — what the game actually compiles and ships.                                                                  |

The game's pin wins. The root submodule pointer should follow it; if they diverge,
update the submodule to match the game's resolved SHA, not the other way around.
Always pin a full commit SHA, never `#main` — a floating branch ref re-resolves
silently on any future install.

## Engine-change release ordering

When the engine changes, the order is fixed:

1. **In `md-rpg`**: commit, push to its own `origin/main`. Note the new SHA.
2. **In the game repo**: update the pinned SHA in `package.json`, run
   `pnpm install`, run `npm test` and `npm run build`, commit (including
   `pnpm-lock.yaml`), push.
3. **At this root**: `git -C md-rpg fetch && git -C md-rpg checkout <sha>`, same
   for the game submodule's new HEAD, then `git add md-rpg the-boy-who-collected-silence` and commit the pointer bump.

The general submodule rule (see `CLAUDE.md`): commits land inside each submodule
first, against its own remote; the root pointer bump is always last and always
deliberate. Never let pointers drift silently.

## Deploy ownership

| Surface          | Deploys to                                                 | How                                                                                                |
| ---------------- | ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Game             | Any static host (web) + App Store / Play Store             | `npm run build` → `out/`; `npm run cap:sync` snapshots it into `ios/`/`android/` for native builds |
| Landing page     | Cloudflare (worker `bellwood`, https://bellwood.mnmls.net) | `wrangler`, per its repo                                                                           |
| Reader extension | Chrome Web Store + Safari port                             | No build step; load unpacked / package per its `README.md`/`SAFARI.md`                             |
| md-rpg           | Nothing today                                              | `publishConfig` is wired for a future npm publish; consumed from git until then                    |

## Why a GitHub dependency (and not a submodule/workspace)

The game previously consumed the engine as a git submodule at `packages/md-rpg`
wired as a pnpm workspace member (`workspace:*`) — see the game repo's
`docs/plans/05-md-rpg-package-extraction.md` for the historical record. That was
replaced by the pinned GitHub dependency. Trade-offs, on record:

**Chosen: pinned GitHub dependency**

- ✚ The game builds standalone anywhere pnpm can reach GitHub — store pipelines,
  fresh clones, CI — with a plain `pnpm install`; no `--recurse-submodules`, no
  workspace machinery.
- ✚ Standard lockfile semantics: `pnpm-lock.yaml` records the exact commit and an
  integrity hash.
- ✚ md-rpg being public makes installs auth-free.
- ✚ One copy of the engine per checkout (in `node_modules`), not three pins of the
  same repo spread across two levels.
- ✖ No in-place edit loop: changing the engine means a separate clone, push, pin
  bump, and reinstall. (Cost accepted — the engine changes rarely now.)
- ✖ No atomic cross-repo change: an engine change and its game-side adaptation are
  two commits in two repos.
- ✖ The engine source in `node_modules` is not editable — easy to forget and
  scratch-edit there; changes vanish on the next install.

**Abandoned: submodule + pnpm workspace**

- ✚ In-place engine editing with an atomic dev loop (edit `packages/md-rpg/src`,
  see it live, commit both sides together).
- ✖ The same engine repo ended up pinned in three places (root submodule, game
  submodule, plus the root's game gitlink transitively) — sync discipline nobody
  kept, and exactly the documentation drift this doc's revision cleaned up.
- ✖ Every standalone clone/pipeline of the game needed `--recurse-submodules` and
  workspace-aware tooling.

## Pin-sync

Keeping the root `md-rpg` submodule pointer equal to the SHA in the game's
`pnpm-lock.yaml` is manual today (step 3 of the release ordering). A small check
script at this root could assert it.
