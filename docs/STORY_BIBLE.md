# Story Bible: The Collectors Universe

The shared mythology and continuity rules spanning all four planned series. Series-specific
craft detail (chapter content, choice design) stays in each series' own docs — this file only
covers what spans them, same rule `ARCHITECTURE.md` uses for the technical side.

## Premise

Scattered through the world are quiet people called **Collectors** — each notices and gathers
something intangible everyone else overlooks. Every Collector is guided, at least briefly, by a
**Keeper**: someone who already knows how to notice, and teaches the skill forward.

Note the double use of "Keeper": it is both this archetype *and* a specific character in series 1,
one of four young travelers who named themselves for what they carried (_The Keeper. The
Listener. The Laugher. And Lyra — who heard me._). Asa is **not** the first Collector; that
generation came decades before him, and their story is what series 1's bonus chapter uncovers.
Three more Collectors remain to be told.

## Continuity model: standalone stories, one chain

Still not a saga — no shared protagonist, and **every series must open and satisfy without
having played the others**. But the connective tissue is deliberate and structural, not
incidental easter eggs. Three rules:

### 1. Every series ends with a bridge bonus chapter

The bonus chapter is where a series hands the universe forward. It is the last thing a reader
sees, and it introduces the next series' protagonist and passes them an object.

Bridges are **gated content** (series 1's is locked behind finding all five puzzles; keep that
pattern). This is the reason the standalone rule above must hold — many players never see a
bridge, so no series may depend on one.

### 2. Every protagonist appears in the previous story, peripherally

A cameo, not a co-lead: a handful of lines, usually unnamed or named once in passing. Enough
that a returning reader recognises them on page one of their own series; not enough to compete
with the ending they're standing in.

### 3. The object chain

Each bridge hands over a physical thing, and the next series opens holding it. This is what
makes the chain load-bearing without making any series a sequel:

| Bridge  | Object                                     | Why it carries                                                                                    |
| ------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------- |
| 1 → 2   | The Keeper's unsent letter to Lyra         | Series 1 leaves it in glass on purpose; series 2 is about exactly that class of object.            |
| 2 → 3   | A fragment of the Keeper's scattered maps  | Undeliverable because the place it shows does not officially exist — a map to an almost.           |
| 3 → 4   | L.'s watch                                 | L. left to find another way in "even if it took his whole life." The watch is what's left of that. |

Objects are proposals, not locks — but the *pattern* is fixed.

### Towns interconnect; Bellwood is the anchor

Series 1's town is named and lived-in across 15 chapters. The universe orbits it rather than
inventing a fresh map each time:

- **Series 1** — Bellwood, and the valley beyond the maps.
- **Series 2** — the dead-letter office, down-valley from Bellwood, where undeliverable mail
  collects at a junction.
- **Series 3** — a town that exists because of a road that was never finished; the Museum is its
  only reason to stop.
- **Series 4** — **Bellwood again, generations later.** Mr. Ticktock's listening houses
  (`chapter-20.md`, `#ch20-bellwood-kept`) grew into the town's character. A reader who played
  series 1 walks into a place they know, changed, and can excavate its history — which is
  exactly what series 4's Curiosity quality is for.

### The four travelers

Series 1's bonus chapter establishes four young travelers who found the garden: **the Keeper**
(carried the maps), **Lyra** (who heard everyone), **T.** — later Mr. Ticktock — (carried the
jokes, then built loud things, then built listening houses), and **L., the Listener** (carried
the questions and the watch; walked away to find another way in; never resolved).

They map onto series 4's four inner qualities, which is why that stat set reads as the universe
closing a rhyme rather than importing an RPG convention:

| Traveler  | Quality       | Basis in the text                                                       |
| --------- | ------------- | ------------------------------------------------------------------------ |
| Lyra      | **Empathy**   | "She listens the way rain falls on a garden — to everyone, evenly."      |
| L.        | **Curiosity** | "L. carries the questions."                                              |
| The Keeper| **Patience**  | Thirty years of waiting; "I think the waiting is over."                  |
| T.        | **Attention** | Filled the world with noise so no one would notice — then built places for noticing. |

**L. is the universe's open thread.** He is the only traveler whose story series 1 does not
close, and the only one with a whole life spent on an almost. He belongs to series 3's material
and is series 4's deep-history question.

### Timeline

Only one gap is fixed; the rest stay loose on purpose, so each series can set its own distance.

| When                        | What                                                                                                       |
| --------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Decades before series 1     | The four travelers find the garden. Lyra dies. The paths are sealed, the maps scattered. L. walks out.      |
| **Series 1**                | Asa, in Bellwood. The Keeper is alive, waiting, and finally hands the notebook on.                          |
| **Series 2**                | Years after series 1's ending — the Keeper's letter has reached the dead-letter office. Gap open.           |
| **Series 3**                | After series 2. Gap open.                                                                                   |
| **Series 4**                | **Generations after series 1** — fixed. Nobody in Bellwood remembers why the listening houses were built.   |

Series 4's distance is the one non-negotiable: the town must have forgotten its own reason, or
there is nothing for the player to excavate.

## Non-negotiables across every series

Inherited from `.agents/skills/cozy-interactive-fiction/references/cozy-craft-guide.md` — these
apply to all four series regardless of mechanic tier:

1. Low stakes — nothing catastrophic is ever truly at risk.
2. Whimsy is present, even in melancholy material.
3. The arc is about growth/healing, not conquest.
4. Community/connection matters more than individual triumph.
5. Every route ends warm. No route ends in failure, loss-without-repair, or punishment.

Promise 5 is the one that mechanic escalation puts under most pressure — see
[The ceiling](#the-ceiling-what-series-4-is-and-is-not) for how series 4's framing resolves that
rather than fighting it.

## The series ladder

| #   | Working title                    | Collects                       | Reader band | Mechanic tier                                                     | Status                                                 |
| --- | -------------------------------- | ------------------------------ | ----------- | ----------------------------------------------------------------- | ------------------------------------------------------ |
| 1   | _The Boy Who Collected Silence_  | Silence / unspoken moments     | Accessible  | Linear, flavor choices only                                       | Shipped — see `the-boy-who-collected-silence/docs/`; bridge proposal in [`SERIES_1_BONUS_REVAMP.md`](SERIES_1_BONUS_REVAMP.md) |
| 2   | _The Last Post_                  | Unsent words / unread letters  | Accessible  | Real branching, multiple endings                                  | Concept — [`SERIES_2_CONCEPT.md`](SERIES_2_CONCEPT.md) |
| 3   | _The Museum of Almost_           | Roads not taken / regret       | Literary    | Branching + light systems (affinity/skill-checks, no fail states) | Concept — [`SERIES_3_CONCEPT.md`](SERIES_3_CONCEPT.md) |
| 4   | _The Listening Town_             | Understandings / people's lives | Literary    | Conversational RPG — living world, inner-quality stats, no combat | Concept — [`SERIES_4_CONCEPT.md`](SERIES_4_CONCEPT.md) |

### On titling

Series 1's title states the formula; **the rest deliberately don't.** Repeating
_"The \_\_\_ Who Collected \_\_\_"_ four times would flatten the universe into a generic
boxed set and telegraph the mythology before the reader earns it. The Collector/Keeper
structure stays as internal mythology — a reader who has played more than one series
discovers the connection, rather than being told it on the cover.

Each series' own concept doc carries a shortlist of alternates; nothing is locked until
that series enters active drafting.

## Escalation rules

**Reading complexity** — two bands, not a chapter-by-chapter drip:

- _Accessible_ (series 1-2): short-to-medium sentences, metaphor-forward, calibrated to
  series 1's existing prose (`the-boy-who-collected-silence/content/chapter-01.md` is the
  reference sample).
- _Literary_ (series 3-4): longer/more ambiguous sentences, more interiority, endings that
  still land warm but can carry more ambiguity getting there.

Escalate demand through narrative complexity and consequence weight, never through vocabulary
difficulty alone.

**Mechanics** — linear → branching → systems-inside-a-story → story-inside-a-world. The
distinction between tiers 3 and 4 is the useful one: series 3 puts systems inside a guided
story; series 4 puts a story inside an explorable place. Each series pulls only the `md-rpg`
roadmap items (see `md-rpg/README.md`) it actually needs, when it needs them. Do not build
ahead of the series that requires the feature.

## The ceiling: what series 4 is, and is not

The universe's endpoint is **not** a conventional text RPG. Zork/Achaea-style parser adventures
and combat RPGs are a well-served genre and a poor fit for a universe whose entire subject is
noticing. The target is closer to **Disco Elysium with the combat removed entirely** —
everything resolved through text, dialogue, and choice:

- **Quests centre on people, not monsters.** The dramatic unit is a person's situation, not an
  encounter.
- **Stats represent inner qualities**, not physical attributes — the working set is
  **Attention, Empathy, Curiosity, Patience**.
- **Conflict resolves through conversation, observation, and understanding.** There is no
  attack verb anywhere in the universe.
- **The world feels alive through NPCs, locations, and history** — not through a battle system.

This is the endpoint the whole ladder should aim at: a world that asks the player to read,
notice, understand, and finally live inside it, rather than conquer it.

### Why this dissolves the cozy-vs-RPG tension

An earlier draft of this bible carried a guardrail defending the cozy promises against
imported RPG mechanics. Most of that tension disappears under this framing — if stats are
inner qualities and conflict is conversational, there is no combat loop and no fail-state to
defend against. What survives as a rule:

- **No lose-states.** A check that doesn't clear changes what the player sees and how a person
  reads — never whether the story continues, and never as punishment. Failure is a different
  understanding, not a worse one.
- **No accumulation-for-its-own-sake.** Inner qualities are cultivated by paying attention, not
  farmed. Nothing in the universe rewards grinding.
- **What's collected is understanding, not loot.** The Collection (series 4's analogue to an
  inventory) holds internalised insights about people and places, not items.

`the-boy-who-collected-silence/docs/GAME_DESIGN.md`'s ban on combat/XP/loot/stat-optimization
was written for that title, but under this framing it holds for the whole universe — series 4
included. `md-rpg`'s v1→v2 non-goal (see `ENGINE_SPEC.md`) still gets deliberately revisited for
series 4, but for a much narrower feature set than a full RPG engine would need; details in
[`SERIES_4_CONCEPT.md`](SERIES_4_CONCEPT.md).

## Shared visual/tonal contract

Root `CLAUDE.md`'s "Shared visual language" section (dark, late-night, `oklch` themes, warm
amber accents, editorial serif display type, reduced-motion animation) applies to all series'
presentation layers. Extend the same discipline to prose tone: cozy, melancholic-but-warm,
reflective — matching series 1's register even as reading band escalates in series 3-4.

## Settled

Recorded so they don't get relitigated:

- **Shared setting, not parallel worlds.** One world, one timeline, anchored on Bellwood.
- **Series connect structurally** — bridge chapters, cameos, and the object chain — while each
  still opens standalone.
- **Series 4 is not a conventional RPG**, and its four qualities are the four travelers.

## Open decisions

- **Umbrella/imprint name** for the four-series set. Since the titles no longer carry the
  formula, the umbrella is what signals "same universe" on a store page. Candidates:
  _The Noticing_, _Quiet Worlds_, _The Collectors_ (kept as an internal-mythology name only if
  it isn't used publicly). Not yet chosen.
- **Do bridge chapters stay gated?** Series 1's bonus is locked behind all five puzzles. Keeping
  the gate makes the universe's connective tissue a reward for attentive readers; ungating trades
  that for reach. A product call, not a craft one — see
  [`SERIES_1_BONUS_REVAMP.md`](SERIES_1_BONUS_REVAMP.md).
- **Whether series 1's bonus chapter actually gets revamped.** Everything downstream assumes it
  does; if it stays as shipped, series 2 needs a different way to inherit the Keeper's letter.
- Final protagonist names, and how long the gaps between series 2 and 3 actually are.
- **Does L. get an answer in series 4?** Deciding this decides whether the universe ends
  warm-and-resolved or warm-and-still-listening.
- Which inner qualities series 3 seeds ahead of series 4 — current recommendation is Curiosity
  and Patience, unnamed in the UI. See [`SERIES_3_CONCEPT.md`](SERIES_3_CONCEPT.md).
