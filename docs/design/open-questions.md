# Open Questions

Decisions the system is currently blocked on or actively split over. Each entry
states the question, the options on the table, and what depends on the answer.

Settle the ones marked **load-bearing** first — other pages cannot be written
until they resolve. For questions already answered, see [Decisions](decisions.md).

## Resolution

### What does a level actually grant?

Settled that [scores are linear in level](decisions.md#scores-are-linear-in-level-power-is-exponential).
Still open is whether a level grants one point to one score, or a budget spread
across several.

One point per level keeps the level gap and \(\Delta\) numerically identical,
which makes every level-difference table exact. A budget breaks that identity
but lets two characters of equal level be genuinely different, which is most of
what character building is for.

### Anchoring the remaining fifteen scores

Settled that [anchors come from contemporary human data](decisions.md#score-0-is-anchored-to-contemporary-human-data),
and Force, Power, Stamina and Latency are done. The other fifteen each need a
named measurement, a median, and a citation — and for Will, Composure,
Projection and the rest, an honest note about what the proxy does not capture.

The largest remaining piece of unglamorous work in the system. Every difficulty
table waits on it.

### Aspects in linear or log space?

Mixed-aspect effect is the dot product of the spell's aspect share with the
target's defence vector. If defences are multipliers, that dot product is a
linear-space operation sitting inside an otherwise logarithmic system, and it
disagrees with the log-space reading for any spell that is not purely one
aspect. Deciding this fixes whether
[aspect advantage](../magic/aspects.md#advantage-is-one-doubling) is ±1 to
\(\Delta\) or a separate multiplier.

## Character

### Which score list is canonical?

**Load-bearing.** The [skill list](../rules/skills.md#the-skill-list) pairs
eight scores; [Ability Scores](../rules/ability-scores.md) defines nineteen.
Pairing nineteen is not viable at 171 combinations, so the fix is to keep the
fifteen skill names and re-parent them onto the nineteen — but that has to be
done deliberately, because several of the nineteen absorb a pair outright.

Note also the name collision: **Composure** is currently both a skill and an
ability score, and the [b rule](../rules/index.md#the-character-term) refers to
the score. One of the two needs renaming.

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

### Do aspects and verbs occupy the same axis?

**Load-bearing.** Each aspect now carries a
[basic database operation](../magic/aspects.md#the-five) — Hylogenesis *is*
Create, Pyrolysis *is* Delete. But [Spell Notation](../magic/notation.md#verbs)
treats the five verbs as operators applying freely to any aspect, giving
thirty-five primitives. Both cannot be true as written.

Three readings, in [The consequence nobody has priced in yet](../magic/aspects.md#the-consequence-nobody-has-priced-in-yet):
aspects absorb the verbs; verbs stay orthogonal and the operation is only
flavour; or the two sit at different layers with the compiler mapping between
them. Until this resolves, neither magic page is stable.

### Five aspects or seven?

Five maps exactly onto the five classical elements and the five database
operations, and gives a wheel with **no neutral matchups at all** — every
exchange is decisive. Seven needs two more elements and two more operations to
justify itself, and buys a third of all pairings being ties, which lets a
caster pick an aspect that is merely irrelevant rather than actively bad.

Aggression versus room to breathe, rather than a question about tidy numbers.

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
