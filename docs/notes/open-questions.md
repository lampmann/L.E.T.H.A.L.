# Open Questions

Decisions the system is currently blocked on or actively split over. Each entry
states the question, the options on the table, and what depends on the answer.

Settle the ones marked **load-bearing** first — other pages cannot be written
until they resolve. For questions already answered, see [Decisions](decisions.md).

## Resolution

### What does a level actually grant?

Settled that [each level multiplies the scores](../rules/ability-scores.md#level).
Still open is whether a level doubles one score, or gives a quantity of
increase to divide between several.

One score per level keeps the level difference and the ratio \(R\) identical,
which makes every level-difference table exact. A budget breaks that identity,
but it lets two characters of the same level be genuinely different, which is
most of what character building is for.

### Anchoring the remaining fifteen scores

Settled that [anchors come from contemporary human data](decisions.md#score-100-is-anchored-to-contemporary-human-data),
and Force, Power, Stamina and Latency are done. The other fifteen each need a
named measurement, a median, and a citation — and for Will, Composure,
Projection and the rest, an honest note about what the proxy does not capture.

The largest remaining piece of unglamorous work in the system. Every difficulty
table waits on it.

### Are aspect defences multipliers or exponents?

Mixed-aspect effect adds the spell's aspect values against the target's defence
values. If the defences are multipliers, a half-fire spell against a
fire-resistant target gets half the resistance. If they are exponents, it gets
the square root. The two disagree for every spell that uses more than one
aspect. Single-aspect spells are the same either way.

## Character

### What is the skill list?

Settled that [the nineteen scores are correct](decisions.md#the-nineteen-scores-are-correct)
and that the skill list restarts from nothing.

Open: which activities become skills, and how many there are. Twenty entries is
a lot to hold in the head. Twelve is easier and loses detail. A proposal is in
the [Scratchpad](scratchpad.md#skill-list-proposal).

Three smaller questions come with it:

- May a skill derive from only one score? If yes, a skill is only a trained
  multiplier over that score.
- Persuasion and Deceit want the same two scores. Merge them, separate them
  with a third score, or accept that only the fiction separates them.
- Which skills use the minimum rule instead of the mean rule?

### What is the skill list?

The FATAL list runs to several hundred entries. The brainstorm's instinct is
that "fighting in melee" and "fighting at range" should sit at the *same tier*
as "investigation" and "recall knowledge" — which implies a much shorter list
than the source material, and a deliberate stance that combat is not mechanically
privileged over the rest of play.

Unresolved: how many skills, and whether the knowledge tree gets its full
academic hierarchy or collapses to a handful of fields.

Note that [the setting is original rather than period-accurate](decisions.md#the-setting-is-original-not-period-accurate),
so the knowledge tree is no longer obliged to mirror a medieval curriculum. It
should be built from what the setting contains — which means the setting needs
enough substance to generate one.

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

### What sets the values in a mixed aspect list?

Settled that [verbs and aspects are correlated](decisions.md#verbs-and-aspects-are-correlated-not-identical),
and that the verb puts its own aspect into the spell. A firebolt is therefore
about 99 percent Pyrolysis and 1 percent Hylogenesis.

Open: what rule gives those numbers. At present 99 and 1 are an estimate.

One candidate, untested: **weight each part by the bits that it contributes.**
The fourth theorem ties the list to complexity, and a verb is one symbol while
its target needs a full specification. A verb would then take a small share by
construction, and the share would fall as the target becomes more complex. This
also predicts that a spell with a simple target has a larger verb share.

### Does the correlation do anything except set percentages?

The correlation certainly changes the aspect list. It is not decided whether it
does anything more.

- **Weight only.** Any verb works with any aspect. The pair only decides the
  list. This is the smaller rule.
- **Weight and cost.** A verb that disagrees with its target costs more mana,
  or takes more strokes, or needs a higher rank. Create Fire would then be
  harder than Create Stone, because Create is Hylogenesis and stone is
  Hylogenesis.

The second option gives casters a reason to prefer some pairs. It also adds a
table that somebody must fill in for all 35 pairs.

### Do aspect matchups exist at all?

**Asked first.** An aspect can have an advantage against another aspect, or all
aspects can be equal.

If matchups exist, aspects drive combat and a caster chooses an aspect against
the opposition. If they do not, aspects only sort spells into groups, and the
defence vector has no purpose.

### Five aspects or seven?

This question depends on the one above. It only matters if matchups exist.

Five maps onto the five classical elements and the five database operations,
and gives a wheel with **no equal pairs at all**. Every exchange has a result.

Seven needs two more elements and two more operations, and makes one third of
the pairs equal. A caster can then pick an aspect that is merely irrelevant
rather than bad.

### Do daemons carry extra variance?

**Needs revisiting.** The wiki currently says
[daemons resolve at lower \(b\)](../magic/notation.md#daemons-should-be-the-optimal-play),
justified by the claim that no binder can prove a daemon's obedience is more
than a statistical tendency.

That claim comes from a section of the source notes now marked outdated, and
the current material undercuts it twice: the anti-daemon movement's objections
are explicitly *not* substantively arguable from an outside view, and the
movement was itself manufactured. If daemons are simply good, then a variance
penalty encodes the luddite position into the mechanics — the opposite of what
the fiction says.

The likely fix is that daemons carry **no** \(b\) penalty; a daemon executes a
verified program exactly as a mage does. Their cost is mana, water and
components, and the real risk is *daemon possession* rather than unreliability.

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
