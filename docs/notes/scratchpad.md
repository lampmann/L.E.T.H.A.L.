# Scratchpad

<div class="notes-banner" markdown>
**Raw notes. Messy on purpose.**

Nothing here is decided. Nothing here is tidy. Half of it is wrong. Add to the
bottom, do not clean up.
</div>

## The score scale changed twice

First version: score = the quantity. Second version: score = log2 of the
quantity, because then the resolution formula becomes a subtraction and the
whole system speaks one unit. Third version: back to the quantity.

The log version was not wrong, but it made every character sheet read like a
lab notebook. `Force 1.36` means nothing to a player. `Force 2.6` means "two
and a half times a normal person", which they can use.

What was lost: the resolution formula was `p = 1/(1+2^(-b·Δ))` with
`Δ = S − D`, one subtraction and one table lookup. Now it is a division and a
power. At `b = 1` this is fine, `p = S/(S+D)`. At other values of `b` somebody
has to raise a number to a power at the table.

**Resolved.** A few cells in a spreadsheet do it, and a character sheet with a
built-in calculator does it later. Not a problem. Do not spend more time on it.

The crit rule survived the change without any edit, which is a good sign. It is
still "a factor of three either way", and it still gives `1/(1+3^b)`.

## Things that the aspect change broke

Each aspect now carries a database operation. But the notation has five verbs
that apply to any aspect. Both cannot be true.

If aspects absorb the verbs, then the notation page loses its verb column and a
spell is a point in aspect space plus arguments. That is cleaner and explains
why five is natural: five elements, five operations.

If verbs stay separate, then "Hylogenesis governs Create" is only flavour, and
the 35 primitives survive.

**Resolved, and by a proof rather than by taste.** Theorem 4 says the aspect
list fixes the complexity. So all pure-Pyrolysis things share one complexity
value. A firebolt will not land on that exact value, so a firebolt is not pure.
It is about 99/1 Pyrolysis to Hylogenesis.

**Correction.** I first wrote that aspects absorbed the verbs and the verb
column dies. Wrong. Verbs and aspects use different symbols and both get
written. They are correlated: the verb puts its own aspect into the spell's
list.

So the notation loses nothing at all. 35 verb-aspect pairs stand. What changes
is that the aspect list is derived from the expression rather than written by
the caster.

Open, and possibly the more interesting question: does the correlation do
anything except set the percentages? If a mismatched pair also costs more, then
Create Stone is cheaper than Create Fire, and casters get a reason to care.
That needs a table of 35 entries. If it is weight only, no table is needed.

Two things fall out that nobody asked for:

- Exactly five pure aspect lists exist, each with one complexity. Those are five
  unique spells, not five classes of spell. That is a strong lore hook. Somebody
  should decide what the five pure spells are.
- The aspect list gives the complexity, so it gives the rank. Two spells with
  the same list must have the same rank. That is a real constraint on spell
  design and it is not written down anywhere yet.

## b, before it was settled

Old idea: `b` high for casters, low for warriors, because inconsistency is the
price of bad play.

Objection: that is not derived from anything. Deadlifting a known weight is one
of the most reliable acts a body performs.

Resolution: `b = 1/(s ln 2)`, where `s` is the spread of luck in doublings. Then
the old idea turns out to be right, but for a different reason. A spell is a
program and runs the same each time. A duel has an opponent who is making your
model wrong on purpose.

Best sentence from that argument, keep it: **low b belongs to contests, not to
warriors.**

## Daemons

Currently the wiki says daemons roll at lower `b`. The reason came from a
passage that is now marked outdated, and the current lore says the anti-daemon
faction is simply wrong.

So the variance penalty encodes the luddite position into the mechanics. That
is backwards. Probably daemons should have no penalty at all, and their cost is
mana, water, components, and the risk of possession.

Not changed yet. Waiting for a decision.

## Skill list versus score list

**Resolved.** Nineteen scores. The skills sheet is outdated. Build the skill
list again from nothing. Drop the Composure skill, because Composure is a
score.

## Skill list proposal

Not decided. A starting point only.

The old list made a skill from each pair of scores. That is backwards. It
generates combinations and then looks for a name. Start from the activity
instead, then ask which scores it needs.

The brainstorm already had the right instinct: "fighting in melee" and
"fighting at range" should sit at the same level as "investigation" and "recall
knowledge". So combat is not privileged, and the list should read like a list
of things people do.

A first cut, by what a character spends time doing:

**Fighting**

- Melee — Precision, Agility
- Missiles — Precision, Acuity
- Grappling — Force, Articulation
- Defence — Agility, Latency

**Moving**

- Athletics — Power, Stamina
- Climbing — Force, Stamina
- Stealth — Agility, Attention

**Making**

- Craft — Precision, Memory
- Medicine — Precision, Memory
- Cooking — Acuity, Memory

**Knowing**

- Investigation — Attention, Memory
- Lore — Memory
- Magecraft — Memory, Will

**Dealing with people**

- Persuasion — Projection, Affect Reading
- Deceit — Projection, Affect Reading
- Command — Projection, Will

**Sensing**

- Sight, Hearing, Smell, Taste, Touch — Acuity, plus the chassis factor

Problems with this cut:

- Persuasion and Deceit use the same two scores. Either merge them, or find a
  score that separates them, or accept that the difference is fiction and not
  numbers.
- Lore takes only one score. Is a one-score skill allowed? The rule says "at
  least 1", so yes, but then a skill is only a trained multiplier.
- Nothing here uses Tempo, Plasticity, Toughness, Recovery or Homeostasis.
  Those five may be scores that no skill needs, which is fine — they act
  directly, without a skill in front.
- The list has 22 entries and it is not complete. Decide the target size first.
  Twenty is a lot to hold. Twelve is easier and loses detail.

## Small things, unsorted

- Autophoresis has no domain yet. Air, Move, and `????????`.
- Light belongs to Pyrolysis or to Anamnesis. Not both.
- Five aspects gives no neutral matchups at all. Seven gives two each. This is
  the real question, not which number is prettier.
- Hitstun with no floor can lock a low-Agility target out of the game forever.
- A bleed clock would be more realistic than a wound track, and would make
  fights much shorter. That is a tone decision, not a realism one.
- The two editions need a rule about what is load-bearing.
- Nation 1 has Polities. Nothing has names yet. Names are for losers.
- Ceterum censeo bears are fish.
