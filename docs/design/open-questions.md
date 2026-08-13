# Open Questions

Decisions the system is currently blocked on or actively split over. Each entry
states the question, the options on the table, and what depends on the answer.

Settle the ones marked **load-bearing** first — other pages cannot be written
until they resolve.

## Resolution

### How is b assigned?

**Load-bearing.** [\(b\)](../rules/index.md#the-skill-factor) sets swinginess,
crit rate, and how much the ability scores matter at all.

- **By activity type**, as the brainstorm has it: high for casting, low for
  martial work, with inconsistency as the price of playing a warrior.
- **Emergent**, from a task term (how completely the rules model the situation)
  plus a character term rising with Composure, Attention and Will.

The objection to the first is that it is the only rule in the system not
derived from a modelled quantity, and it runs backwards from the physics —
deadlifting a known weight is nearly deterministic, casting into unmodelled
conditions is not. The objection to the second is that it costs the design its
class identity, and requires the GM to set a number per situation.

### What anchors the baseline?

**Load-bearing.** Score 0 is "the median adult human", but that has to point at
something.

- **Published human performance data** — grip dynamometry, VO₂max
  distributions, simple reaction time norms. Every score gets a real referent
  and the system earns the word simulationist.
- **A fictional baseline set by hand**, tuned for play.

This changes every table in the book, so it wants deciding before any of them
are written.

### Is level linear or logarithmic?

The notes want power, narrative relevance and wealth to be **linear** in level.
Ability scores are **logarithmic**. Both cannot hold at once:

- If scores rise linearly with level, real capability doubles per level and
  power is *exponential* in level.
- If power is linear in level, scores must rise as \(\log_2(\text{level})\),
  which means a level 5000 character is only about 12 points above a level 1.

The second reading makes "level 5000" meaningful as a statement about the
world rather than about a character sheet, and keeps \(\Delta\) inside the
range dice can express. The first matches most players' intuitions about what
levelling feels like.

### Aspects in linear or log space?

Mixed-aspect effect is the dot product of the spell's aspect share with the
target's defence vector. If defences are multipliers, that dot product is a
linear-space operation sitting inside an otherwise logarithmic system, and it
disagrees with the log-space reading for any spell that is not purely one
aspect. Deciding this fixes whether
[aspect advantage](../magic/aspects.md#advantage-is-one-doubling) is ±1 to
\(\Delta\) or a separate multiplier.

## Character

### How do skills combine with scores?

Both recorded proposals agree that skills inherit from other skills and scores
— juggling inherits from hand-eye coordination and reaction speed. They differ
on what happens when a task needs several:

- **Vermahn–Goldwynn**: make multiple checks, one per contributing stat.
- **Stahlmann–Greenberg**: make one check, taking the **minimum** of the
  contributing stats. Skills may also carry prerequisites; failing to meet one
  incurs a penalty, but prerequisites do not enter the minimum.

Stahlmann–Greenberg is one roll instead of three and matches the
[bottleneck rule](../rules/ability-scores.md#combining-scores) already adopted
for scores. Vermahn–Goldwynn models compound failure more honestly — a juggler
really can drop the pattern in several independent ways.

### What is the skill list?

The FATAL list runs to several hundred entries. The brainstorm's instinct is
that "fighting in melee" and "fighting at range" should sit at the *same tier*
as "investigation" and "recall knowledge" — which implies a much shorter list
than the source material, and a deliberate stance that combat is not mechanically
privileged over the rest of play.

Unresolved: how many skills, and whether the knowledge tree gets its full
academic hierarchy or collapses to a handful of fields.

## Combat

### How does hitstun scale?

Flat per weapon is easiest to run. Scaling with damage is more realistic but
risks unrecoverable lock-downs against low-Agility targets — if every hit
pushes the victim's priority back further than the attacker's endlag, they
never act again. Whatever the rule, it needs a floor guaranteeing the victim
eventually gets priority.

### Damage falloff: multiplier or Δ penalty?

[Range bands](../rules/combat.md#range-bands) need a mechanism. A \(\Delta\)
penalty is consistent with the rest of the system and composes with everything
else; a damage multiplier is more intuitive and keeps a spear *accurate* but
feeble at range 0, which may be the more realistic reading.

### How far does the wound system go?

A per-location condition track is more realistic than hit points. A bleed clock
would be more realistic still, since real trauma is dominated by blood loss and
shock rather than accumulating track steps. A bleed clock also shortens fights
considerably, which is a tonal decision as much as a realism one.

### Grid and geometry

Range bands, projectile tracing and the `⊙ within` operator all assume a graph
of nodes. Unsettled: square grid, hex grid, or abstract node graph, and how
diagonal distance works for reach weapons.

## Magic

### Seven aspects or eight?

Seven gives the tria prima plus the four classical elements, in order, with a
clean cycle where each aspect beats two and loses to two. Eight makes the count
a power of two and allows a genuinely neutral aspect alongside a seven-cycle —
at the cost of letting a caster opt out of the matchup system, which the notes
already flag as the least interesting option available.

### How much variance do daemons carry?

If [daemons are the optimal play](../magic/notation.md#daemons-should-be-the-optimal-play),
their cost is variance — a lower \(b\) than the mage would roll. Open: the size
of that penalty, whether it differs per daemon generation, and whether fifth-
and sixth-generation daemons close the gap entirely. If they do, the setting's
central anxiety stops being mechanically expressed at the top end, which may be
exactly right.

### Mana economy

Mana is stated to be uncorrelated with rank, not to regenerate within a duel,
and to be distributed lognormally. Whether L.E.T.H.A.L. inherits that wholesale
from the duel simulator or needs a campaign-scale regeneration rule is open.

## Content and edition

### What separates the two editions?

*Less Than L.E.T.H.A.L.* is the expurgated edition. Unresolved: whether it is
the same book with sections removed, or a genuinely separate presentation —
and, mechanically, whether anything in the removed material is load-bearing for
subsystems the expurgated edition keeps. If the two editions must produce
identical outcomes at the table, the adult material has to be strictly additive.

### Undecided content proposals

Recorded from the brainstorm, not yet designed and not yet adopted:

- Sex and gender as separate character options with mechanical effects,
  including a dysphoria penalty when they differ.
- Attractiveness as a mechanically live stat, and the associated "mogging"
  interaction.
- A trait giving martial or casting aptitude by sex.
- An antagonist religion written as a real-world metaphor.

Each of these is a content decision rather than a systems one, and each will
read very differently depending on execution. They are listed here so they are
not lost, not because the system currently depends on any of them. The
mechanical hooks they would need — Projection, the appearance clause, and
opposed social checks — already exist and do not require these proposals to
function.
