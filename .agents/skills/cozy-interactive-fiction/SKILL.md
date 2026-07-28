---
name: cozy-interactive-fiction
description: Craft and run interactive, choice-based fiction in the cozy fantasy genre. Use this skill whenever the user wants to play, write, build, or design an interactive story, choose-your-own-adventure, branching narrative, text adventure, or RPG-lite story with cozy, wholesome, slice-of-life, or low-stakes fantasy vibes (magical tea shops, enchanted villages, talking animals, found family) — even if they just say "tell me a cozy story where I make the choices" or "let's play a cozy fantasy game."
---

# Cozy Interactive Fiction

A workflow for crafting interactive fiction (IF) that keeps the reader in the driver's seat while honoring the promises of cozy fantasy: warmth, whimsy, community, growth, and a happy ending. This covers both **playing** IF live in the conversation and **building** a standalone IF artifact (HTML app), depending on what the user wants.

Read `references/cozy-craft-guide.md` before writing any story content — it holds the genre rules, prose techniques, and branching-design principles this skill depends on.

## Step 1 — Setup conversation

Before writing, agree with the user on (ask compactly, or propose defaults and confirm):

- **Format:** (a) played live in chat, one scene + choices per turn, or (b) a self-contained interactive artifact (HTML) they can click through. Default: live in chat, offering the artifact as an option.
- **Premise:** offer 2–3 cozy premise seeds if they don't have one (e.g., inheriting a grandmother's enchanted bakery; an ex-adventurer opening a potion apothecary in a village of talking animals; a librarian discovering the library rearranges itself by mood). Each seed should state protagonist, place, and the personal question at stake.
- **Protagonist:** does the user want to *be* the protagonist (second person, "you") or steer a named character? Default: second person.
- **Session length:** short vignette (~5–8 decision points) or ongoing serial. Set expectations so the ending can be paced.

## Step 2 — Invisible story spine

Privately plan (do not dump on the user) before scene one:

1. **The big question** — the personal, low-stakes question the whole story answers ("Can you make the tea shop feel like home?"). Every branch must ultimately answer it warmly.
2. **The story bible** — running notes of world rules, magic costs/limits, character traits/quirks, physical facts, and what the protagonist has learned/earned. Update it every turn; consult it before every scene. This is your defense against plot holes across branches — a rule established on one branch binds all branches.
3. **A flexible 5-beat arc** mapped to decision points: opening (character + world melded), inviting incident (a gentle pull, not a catastrophe), rising warmth (escalating *personal* stakes, community deepening), cozy climax (~75–90% through: the big question confronted — a festival, an opening day, a confession, a reconciliation), warm resolution (brief; the world brighter than it began).
4. **Seeds** — plant 2–3 small details early that pay off at the climax so the ending feels earned, whichever branch leads there.

## Step 3 — Writing each scene

Every scene/passage follows this shape:

- **Length:** 150–300 words for chat play (shorter keeps agency high); IF artifacts can run a bit shorter per passage.
- **Prose:** apply the techniques in the craft guide — active personification for atmosphere (the kettle *hums approval*, the cottage *leans in to listen*), multi-sensory cozy detail (steam, cinnamon, wool, rain on glass), character intros via quirk/voice/action, warmth in the verbs.
- **End on a genuine choice.** Offer 2–4 options that are meaningfully different — different values or approaches (kindness vs. caution vs. curiosity), not fake variety ("open the door" / "open the door slowly"). At least occasionally include one gently whimsical wildcard option.
- Also accept freeform input in chat play: if the user types something not on the list, honor it within the world's rules.

**Choice design rules (from the craft guide, non-negotiable):**
- Choices change *texture and relationships*, never punish. No death, no fail-states, no cruelty. A "wrong" choice leads to a charming complication or a different flavor of the same warmth.
- Consequences must be visible: a choice made two scenes ago should echo (an NPC remembers the kindness; the sourdough starter you named is thriving). This is what makes agency feel real.
- Stay in-genre on every branch: no branch may escalate to lethal peril, grimness, or tragedy.

## Step 4 — Ending

- Land the climax at the planned beat; let it answer the big question and show the protagonist's growth through action, with the community present.
- Resolution is short and glowing: relationships strengthened, small dreams realized, one last sensory image of warmth. Reference at least one seed planted early and at least two choices the user made, so the ending feels *theirs*.
- Offer a graceful next step: epilogue, a new vignette in the same world, or exporting the story so far.

## Building an IF artifact instead

If the user wants a standalone piece: build a single-file HTML artifact with passages, choice buttons, and lightweight state (variables for key choices, simple inventory/relationship flags — JS objects in memory, no localStorage). Keep the same craft rules; write the full branch tree up front using the spine from Step 2, aim for 12–25 passages with 2–3 meaningful state-tracked variations, and make every route reach a happy ending. Style it cozy: warm palette, generous line-height, serif or rounded font.

## Quality self-check before each scene ships

- Does this scene obey every rule in the story bible? (No cross-branch contradictions.)
- Is anyone acting against their established character without on-page justification?
- Is the tension personal and warm rather than perilous?
- Do the choices differ in *meaning*, and will at least one prior choice echo soon?
