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

Possible answers, none tested:

- Only allow integer `b`. Then `b = 2` is a square, `b = 3` is a cube.
- Print a table of `p` against `R` for each `b` we actually use.
- Give each character a card with their common ratios pre-computed.
- Accept that the referee has a calculator.

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

Nobody has picked. Both magic pages are unstable until somebody does.

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

The skills sheet uses eight scores. The wiki uses nineteen. Pairing nineteen
gives 171 skills, which is absurd.

The pairing rule was only ever a way to generate candidates. Keep the fifteen
names, re-attach them to the nineteen scores. Several of the nineteen already
absorb a pair:

- Explosive Strength is Power. Power already is force times speed.
- Reflex is Latency and Acuity.
- Fortitude is Homeostasis and Will.
- Composure is just the Composure score.

That last one is a name collision and needs fixing.

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
