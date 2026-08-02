# Series 3 Concept: The Museum of Almost (working title)

Universe rules, non-negotiables, and the full series ladder live in [`STORY_BIBLE.md`](STORY_BIBLE.md) —
this doc only covers what's specific to series 3.

## Status

Concept. No repo/submodule exists yet. Nothing below is locked. Depends on series 2 shipping
first and validating the branching engine work — don't start series 3 engine investment before
series 2 is in active development.

## Title

**_The Museum of Almost_** — names a place rather than a person, which suits a series about
curated, catalogued near-misses and gives the systems tier a natural container (rooms, exhibits,
a collection with an order to it). Does not repeat series 1's construction.

Alternates, roughly in order of preference: _Everything That Almost Happened_ ·
_The Weight of Maybe_ · _A Thousand Doors, One Room_ · _What the River Kept_.

## Logline

Someone who collects the roads not taken — other people's abandoned choices, half-lived
possibilities, the version of a life that got set down — and has to face the ones they set down
themselves.

## Why this Collector theme fits the mechanic escalation

The theme is literally about alternate paths and their weight. Branching alone (series 2) isn't
enough to carry that — series 3 needs the *consequences* of choices to accumulate and be
legible to the player as a system, not just as remembered narrative beats. That's what
justifies introducing light systems here rather than in series 2.

## Bridge in — what series 2 hands over

Series 2's bonus chapter introduces this protagonist and hands them **a fragment of one of the
Keeper's scattered maps**, undeliverable because the place it shows does not officially exist.
Series 3 opens on it: the first exhibit, and the reason the Museum exists at all.

The backing mythology is already in series 1's bonus chapter — after Lyra's death the four
travelers sealed the paths and scattered the maps to keep the garden from being found, and the
Keeper confesses she could not burn all of them. That is the universe's founding regret, and
this series is where it gets catalogued.

**L., the Listener** — the traveler who walked out saying he would find another way in "even if
it took his whole life" — is this series' richest material. A man who spent a lifetime on an
almost belongs in a museum of them.

Standalone as always: a player arriving here cold meets a curator, a strange map, and a building
full of near-misses, with no homework.

## Bridge out — what series 3 hands to series 4

Series 3's bonus chapter introduces series 4's protagonist and passes them **L.'s watch** — the
one object in the collection that stopped being an almost. Whether L. ever found his way in is
the question series 4 inherits.

## Reader band & craft target

First series in the *literary* band. Longer, more ambiguous sentences; more interiority; more
existential/adult thematic weight (regret, the lives not lived) than series 1-2 carry. Endings
must still land warm per the cozy promises — ambiguity is allowed in how the story gets there,
not in whether it resolves with care.

## Mechanic tier

Branching (inherited from series 2) plus light systems: affinity- or skill-check-style gating
that gives accumulated choices legible weight, without ever producing a fail state.

## Engine requirements (md-rpg)

Partially covered already — `affinity.*` and `vars` plus `@if` can gate content today with no
engine changes. The likely addition needed is the roadmap's numeric helper functions
(`min`/`max`/`clamp`, etc. — see `md-rpg/README.md`) so stat math reads as a coherent system
rather than ad hoc conditionals. Smaller lift than series 4's engine set; validate exact need
once series 3 outlining starts — don't build the numeric-helpers work speculatively before then.

## Cozy promises

Skill-check/affinity gates change *what* content a player sees or *how* a relationship reads —
never whether the player "passes." No hidden game-over state. A low-affinity path is a
different, still-warm story, not a worse one.

## Bridge to series 4

Series 4 runs on four inner qualities — **Attention, Empathy, Curiosity, Patience** (see the
story bible's ceiling section). Series 3 is the natural place to seed one or two of them
quietly, so that series 4 reads as an arrival rather than a genre swerve. Curiosity and
Patience fit this material most obviously — a series about unlived choices is already about
how long someone is willing to sit with a possibility.

If seeded here, keep them unnamed or barely-surfaced in the UI; series 4 is where they become
a legible system the player reads and reasons about.

## Open questions

- What exactly accumulates — is it affinity with specific characters, a single running "regret"
  or "peace" metric, or several independent tracks?
- Which (if any) of series 4's four inner qualities get seeded here — see the bridge section
  above.
- Protagonist identity/age — literary band suggests an adult protagonist, but not required by
  the theme.
- Relationship to series 1-2's setting, if any.
