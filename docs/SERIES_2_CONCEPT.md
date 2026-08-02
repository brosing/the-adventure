# Series 2 Concept: The Last Post (working title)

Universe rules, non-negotiables, and the full series ladder live in [`STORY_BIBLE.md`](STORY_BIBLE.md) —
this doc only covers what's specific to series 2.

## Status

Concept. No repo/submodule exists yet. Nothing below is locked.

## Title

**_The Last Post_** — carries a double meaning (the final delivery / the last mail collection of
the day) and, deliberately, does not repeat series 1's _"The \_\_\_ Who Collected \_\_\_"_
construction. See the titling note in the story bible.

Alternates, roughly in order of preference: _The Undelivered_ · _Postmarked Nowhere_ ·
_Everything I Meant to Say_ · _The Post Office at the End of the Street_.

## Logline

Someone who collects the letters people never sent — found in drawers, left unfinished, torn up
and taped back together — and, in learning to read what was never said, has to decide what to
finally say themselves.

## Why this Collector theme fits the mechanic escalation

Series 1's silence was passive and receptive — a linear game matched that. Letters are
*exchanged* between people; the mechanic escalation from linear to real branching only makes
sense once the theme involves genuine relational forks. Series 2 is where the universe
introduces choices that diverge, not just choices that flavor a fixed path.

## Bridge in — what series 1 hands over

Series 1's bonus chapter (see [`SERIES_1_BONUS_REVAMP.md`](SERIES_1_BONUS_REVAMP.md)) ends with
the protagonist appearing as a dead-letter clerk at the Bellwood crossroads, taking the Keeper's
unsent letter to Lyra into her sack without knowing whose it is.

**Series 2 opens on that letter**, years later — still unfiled, undeliverable, and impossible to
throw away. Inherited from series 1 and already established in its text: the **Room of Unspoken
Words** (`chapter-19.md`) — "millions of bottled sentences, waiting to become light" — which is
this series' core image, not a new invention. The dead-letter office sits down-valley from
**Bellwood** at a mail junction.

None of this is required reading. A player who never unlocked series 1's bonus chapter meets the
letter as an ordinary mystery.

## Bridge out — what series 2 hands to series 3

Series 2's own bonus chapter introduces series 3's protagonist peripherally and passes them **a
fragment of one of the Keeper's scattered maps** — undeliverable precisely because the place it
shows does not officially exist. A map to an almost, which is series 3's entire subject.

## Reader band & craft target

Accessible band — same calibration as series 1. Reference sample:
`the-boy-who-collected-silence/content/chapter-01.md`. Sentence length and vocabulary should
not escalate from series 1; what escalates is *choice consequence weight*.

## Mechanic tier

Real branching, multiple distinct endings. This is the first series where a choice can lead
players to meaningfully different scenes, not just different flavor text before convergence.

## Engine requirements (md-rpg)

Confirmed engine gap (from `md-rpg/src/parser.ts` / `engine.ts`): scene ids are globally unique
across the whole story, and re-entering a scene re-runs its body unless `@once` is set. This
blocks a clean branching structure with converging/diverging paths. Needed before drafting
begins in earnest:

- Chapter/zone-scoped scene ids (from `md-rpg/README.md`'s roadmap) — the smallest slice of the
  9-item roadmap, not a full engine rewrite.

**Recommended validation step**: before committing to a full chapter outline, write a 2-3 scene
branching spike using the *current* engine to directly observe the re-entry behavior, rather
than planning purely off the README's description of it. Run it against `md-rpg`'s `node:test`
suite to confirm no regressions once the scoped-id fix lands.

## Cozy promises

Fully in effect, unchanged from series 1. Branches diverge in tone, relationship outcome, and
what the player learns — never in success vs. failure. Every ending is a different kind of warm,
not a "good" ending and "bad" endings.

## Open questions

- Protagonist name, age, and setting — do they share series 1's world/era, or a new one under
  the same Collector mythology?
- How many distinct endings, and how much do they actually diverge in content vs. just tone?
- Does a Keeper appear, and is there any deliberate echo of series 1 (a shared object, a
  place-name, a line of dialogue) — per the story bible, optional and non-load-bearing either way.
