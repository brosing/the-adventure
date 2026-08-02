# Series 4 Concept: The Listening Town (working title)

Universe rules, non-negotiables, and the full series ladder live in [`STORY_BIBLE.md`](STORY_BIBLE.md) —
this doc only covers what's specific to series 4. Read the bible's **"The ceiling: what series 4
is, and is not"** section first; it defines the target this whole document builds toward.

## Status

Concept. No repo/submodule exists yet, and no engine work should start until series 3 has
shipped and validated its lighter systems. This is the last and largest lift in the universe —
sequenced last on purpose.

## Title

**_The Listening Town_** — names the place and the verb at once. The town is the system (NPCs,
locations, history), listening is the only real mechanic. Does not repeat series 1's
construction.

Alternates, roughly in order of preference: _Everyone Here Is Someone_ · _The Town That
Remembers You_ · _The Quiet Hours_ · _The Long Way Home_.

## What this is

**Disco Elysium with the combat removed entirely** — every interaction text and choice based.
Not Zork, not Achaea, not a combat RPG with the numbers filed off. The design target:

- **Quests centre on people, not monsters.** The dramatic unit is a person's situation — a
  grudge nobody remembers starting, a shop closing, someone who stopped leaving their house.
- **Stats represent inner qualities**: Attention, Empathy, Curiosity, Patience.
- **Conflict resolves through conversation, observation, and understanding.** There is no
  attack verb.
- **The world is alive through NPCs, locations, and history** — the town has a past the player
  can excavate, and people who were already living there before the player arrived.

## Logline

A traveller arrives in a town where everyone is mid-story, and the only way through is to
listen long enough to understand — first them, and eventually why you came.

## Bridge in — the town is Bellwood

Series 4 does not invent a town. It returns to **Bellwood, generations after series 1**, and the
premise is already written into series 1's ending — `chapter-20.md` (`#ch20-bellwood-kept`):

> Instead, he began building **listening houses**: small places where people could sit quietly,
> share stories, speak honestly, grieve, remember, and dream.

Mr. Ticktock — the man who had spent a lifetime manufacturing noise so nobody would find what
he helped bury — built the first listening houses in the last chapter of series 1. Series 4 is
the town those houses made, long enough later that nobody remembers why they were built. A
player who read series 1 walks into a place they know and can excavate its history; a player who
didn't gets a town with an unusual civic habit and a past worth asking about. That excavation is
precisely what the Curiosity quality is for.

Series 3's bonus chapter hands this protagonist **L.'s watch**. Whether L. — the traveler who
left to find another way in "even if it took his whole life" — ever succeeded is the universe's
last open question, and the natural spine for series 4's deep-history quest line.

## Bridge out

As the final series, series 4's bonus chapter closes the chain rather than extending it. Open
question whether it hands anything to a reader (a fifth series, a new Collector, an invitation)
or deliberately ends the handoff — see open questions below.

## The four qualities are the four travelers

Series 1's bonus chapter establishes four young travelers: the Keeper, Lyra, T. (later Mr.
Ticktock), and L. the Listener. Series 4's stat set is those four people — Empathy is Lyra,
Curiosity is L., Patience is the Keeper, Attention is T. Full mapping and textual basis in the
story bible. This is why the stats read as the universe closing a rhyme rather than as an RPG
convention bolted on at the end.

## Reader band & craft target

Literary band, same tier as series 3. No further escalation in prose complexity — the
escalation in series 4 is entirely in world density and systems, not sentence difficulty.

## The four inner qualities

The working set, per the direction above. Each is a *way of paying attention*, and each unlocks
a different kind of content:

| Quality       | What it does                                                                              |
| ------------- | ----------------------------------------------------------------------------------------- |
| **Attention** | Surfaces physical/environmental detail — what a room, an object, or a face is giving away. |
| **Empathy**   | Surfaces what someone means underneath what they're saying.                                |
| **Curiosity** | Opens new lines of questioning; unlocks history, lore, the town's past.                    |
| **Patience**  | Unlocks content gated on _not_ pushing — staying, waiting, returning later.                |

Design notes:

- Qualities are **cultivated, not farmed** — they grow from how the player chooses to engage,
  and nothing in the game rewards grinding them.
- Borrowing Disco Elysium's strongest text-native device: qualities can **speak as inner
  voices**, interjecting into scenes. This is expensive in writing volume and should be scoped
  deliberately, not applied to every scene.
- Whether a fifth quality is needed (something like Courage or Honesty) is open. Four is clean
  and each maps to a verb the universe already cares about.

## The Collection (inventory analogue)

Series 4's equivalent of an inventory holds **internalised understandings**, not items — the
direct descendant of series 1's keepsakes and the universe's Collector mythology. An
understanding is acquired, sits for a while, and then changes how the player reads the world
(closest existing reference: Disco Elysium's Thought Cabinet).

This replaces item/loot inventory entirely. Nothing in series 4 is equipment.

## Skill checks without failure

Checks exist and matter, but never fail the player:

- A check that doesn't clear yields **a different understanding, not a worse one** — a
  misreading the player can later revisit, or a door that stays closed while another opens.
- **Recommend deterministic, threshold-based checks over dice.** If there are no fail states,
  randomness mostly adds noise; determinism means the qualities the player cultivated always
  pay off legibly, which is the entire point of the stat system. This also removes seeded RNG
  from the engine requirements below.
- No hidden game-over state, no soft-locks, no timers that punish.

## Engine requirements (md-rpg)

Narrower than a full RPG engine would need — the no-combat, no-loot, no-dice framing cuts
roughly a third of `md-rpg`'s roadmap (`md-rpg/README.md`). Likely needed, in dependency order:

1. **Chapter/zone-scoped, revisitable scene ids** — the hard requirement. A town hub with
   locations the player returns to is exactly the case md-rpg's README flags as broken today
   (globally-unique ids, scene bodies re-running on re-entry). May already exist from series 2.
2. **Richer value types / keyed collections** — for the Collection and the quality set.
3. **A bounded stats namespace** — the four inner qualities, with sane min/max.
4. **Numeric helper functions** (`min`/`max`/`clamp`) — may already exist from series 3.
5. **Loop/generator constructs for dynamic choice menus** — dialogue trees plus quality-voice
   interjections need choice lists built from state rather than hardcoded.
6. **User-defined expression macros** — quality-check syntax will be written hundreds of times;
   a macro keeps chapter Markdown readable.
7. **Save-data versioning** — `SaveData` has no version field today, and a world this stateful
   will need migrations.

**Explicitly dropped** from the earlier full-RPG plan: seeded RNG (see the deterministic-checks
argument above) and any items/inventory store (the Collection is understandings, modelled by
item 2).

Items 5-6 require grammar changes to the hand-rolled expression evaluator
(`md-rpg/src/expression.ts`), which has no function-call syntax today — real engineering work,
not configuration. Treat the whole set as an `md-rpg` major version and update `ENGINE_SPEC.md`'s
non-goals section explicitly rather than silently contradicting it.

## Cozy promises

Fully in effect. Under this framing they mostly hold by construction rather than by guardrail —
there is no combat to sanitise and no loot economy to resist. The rules that still need active
enforcement: no lose-states, no grind incentives, and endings that land warm even when the
town's histories are sad.

## Open questions

- Is there a fifth quality, or do four carry it? Note the four-travelers mapping above argues
  strongly for exactly four.
- Does series 4's bonus chapter close the chain or open a fifth series?
- Does L. get an answer? Deciding this is deciding whether the universe ends warm-and-resolved
  or warm-and-still-listening.
- How much inner-voice writing is affordable? This is the single biggest scope risk in the
  series — DE's voice system is enormous. Consider restricting voices to key scenes.
- Structure: one town explored freely, or a road-trip across several smaller places? Affects how
  hard requirement 1 above bites.
- Does the protagonist's own reason for arriving unlock progressively as a quest line, or is it
  known to the player from the start?
