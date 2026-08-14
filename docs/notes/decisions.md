# Decisions

<div class="notes-banner" markdown>
**This is a design note, not a rule.** For the rules, see
[Core Resolution](../rules/index.md).
</div>

A record of settled choices: what we decided, why, and what it costs.
Unsettled items are in [Open Questions](open-questions.md).

Each entry stays here. If a choice reverses, the entry gets an amendment. It is
not deleted. What we tried and rejected is worth more than a tidy list.

## Verbs and aspects are correlated, not identical

**Decided.** A verb and an aspect use different symbols. A caster writes both.
The two are not independent: each verb carries its own aspect, and that aspect
enters the spell's aspect list.

**Amended.** An earlier version of this entry said that aspects absorb the
verbs, and that the verb column dies. That was wrong. The correlation acts on
the aspect list, not on the notation. The verb column stays, and 35 verb-aspect
pairs stay available.

The reasoning that produced the mix is unaffected, and it comes from the fourth
theorem, \(A(x) = A(y) \implies K(x) = K(y)\):

1. Two pure-Pyrolysis objects have equal aspect lists, so they have equal
   complexity. Every pure aspect therefore has **exactly one** complexity, not
   a range.
2. A firebolt has no reason to land on that exact complexity. So a firebolt is
   not pure Pyrolysis.
3. The verb explains why. A firebolt uses the Create verb, and Create carries
   Hylogenesis. The result is near 99 percent Pyrolysis and 1 percent
   Hylogenesis.

This also agrees with the third theorem, which puts a complex object either
near one pure aspect or at five equal values. A largest value of 0.99 sits in
the first group.

**Consequences:**

- The aspect list is **derived**, not written. It follows from the verbs and
  the targets in the expression.
- There are exactly five pure aspect lists. Each is a single object, not a
  class. A pure spell also cannot use a verb of another aspect, or the verb
  would spoil the purity.
- The aspect list gives the complexity. Two spells with the same list have the
  same complexity, so two spells of different rank need different lists.
- Nothing in the notation is retired. Verbs, handles, metaprogramming,
  modifiers, predicates and the rank ladder all stand.

See [Verbs and aspects are correlated](../magic/aspects.md#verbs-and-aspects-are-correlated).

## Rules are written in Attempto Controlled English

**Decided.** Every rule appears twice: once in ACE 6.7, once in ordinary
English. The ACE version is the rule. The English version explains it.

ACE is a subset of English with exactly one meaning per sentence. Ordinary
rules text is ambiguous, and a reader cannot always tell what a conjunction
joins or what a phrase modifies. ACE removes that class of fault, because the
grammar decides.

**Consequences:**

- Rules pages carry an ACE block. The prose after it is commentary.
- Tables and examples stay in ordinary English. A table is data, not a rule.
- Design notes stay in ordinary English. An argument needs it.
- Writing a rule now takes longer, and a writer must know the ACE grammar.
- Every ACE block must be tested in the APE parser. The machine that builds
  this wiki cannot reach the parser, so **no block is verified yet**.
- ACE cannot state a rule that we cannot state precisely. This is a feature.
  If a rule resists ACE, the rule is vague, and the vagueness was already
  there.

See [Rule Language](../rules/ace.md).

## The nineteen scores are correct

**Decided.** The wiki's nineteen ability scores are the score list. The eight
scores in the old skills spreadsheet are outdated.

**Consequences:**

- The old skill list is dead. It made a skill from each pair of eight scores,
  which gives 171 combinations at nineteen scores.
- The new skill list starts from activities and then finds the scores that each
  activity needs.
- The **Composure** skill is removed. Composure is a score. No skill may take
  the name of a score.
- Five scores may end up with no skill above them: Tempo, Plasticity,
  Toughness, Recovery, Homeostasis. That is acceptable. Those scores act
  directly.

## Scores are linear in the quantity

**Decided.** A score is a measured quantity, divided by the quantity for a
median adult. A median adult is 1.00. A score of 2.6 is 2.6 times that.

**This reverses an earlier decision.** The wiki previously defined a score as
\(\log_2\) of the quantity, so that a score of +1 meant one doubling. That
version is recorded below under *Amended*.

**Consequences:**

- The [resolution formula](../rules/index.md) is
  \(p = S^b / (S^b + D^b)\), which uses the ratio \(S/D\) directly. This is
  the original form from the brainstorm, not a derived one.
- Arithmetic at the table is a division and a power, instead of a subtraction
  and one table lookup. At \(b = 1\) this is easy: \(p = S/(S+D)\). At other
  values of \(b\), somebody must raise a number to a power.
- A character sheet is readable. `Force 2.6` says "two and a half times a normal
  person". `Force 1.36` said nothing to a player.
- The critical rule did not change. It is still a factor of three either way,
  and it still gives \(1/(1+3^b)\).
- Aspect advantage is now "multiply the score by 2" instead of "add 1".
- Skills combine by the **geometric mean** instead of the arithmetic mean. The
  two are the same operation, written in different units.

### Amended: the logarithmic version

The previous decision made a score \(\log_2\) of the quantity. Its advantage
was that the resolution formula became
\(p = 1/(1+2^{-b\Delta})\) with \(\Delta = S - D\), so the only arithmetic
at the table was one subtraction and one lookup in a fixed table.

Its cost was legibility. Every number on a character sheet was a logarithm, and
a player had to convert before the number meant anything.

We chose legibility.

## b is the reciprocal of task noise

**Decided.** \(b = 1/(s \ln 2)\), where \(s\) is the spread of unmodelled
variation measured in doublings. It is a property of the situation, measured,
not assigned by activity class.

The derivation is short: if an action succeeds when \(\Delta + \varepsilon > 0\)
with logistic noise of scale \(s\), the success probability is our curve
exactly. The parameter that looked arbitrary was a noise measurement.

**Consequences:**

- The original instinct — high \(b\) for casting, low for martial work — is
  vindicated, but by mechanism rather than by class. A spell is a program that
  compiles and runs; a fight is a contest against an adversary generating
  variance on purpose.
- The counter-argument that deadlifting a known weight is deterministic is
  *accepted*: it is high \(b\). It simply is not a contest. Low \(b\) attaches
  to contests, not to warriors.
- Expertise raises \(b\), because experts are measurably more consistent, not
  merely better. The two sources of noise add in quadrature.
- Being wounded, exhausted or frightened lowers \(b\), which ties the combat
  system to the resolution system without a new subsystem.
- \(b\) now has a checkable referent, so a difficulty entry can state its noise
  instead of asserting a number.

See [Where b comes from](../rules/index.md#where-b-comes-from).

## Skills combine by geometric mean, not minimum

**Decided.** A skill takes the **geometric mean** of its two scores by default,
and the **minimum** where the fiction has a hard limit.

The three candidate rules are one family — the constant-elasticity-of-
substitution production function at different elasticities — so the question is
how far two capacities substitute for each other, which varies per skill.

**Consequences:**

- Minimum is rejected as a default because it discards real information: at
  Strength +2 / Speed 0 a character is four times stronger than baseline, and
  minimum calls them average.
- The geometric mean is the only rule that keeps a skill on the same scale as
  its scores, which the
  [anchored difficulties](../rules/ability-scores.md#anchor-values) require.
- Summing is correct physics in the one case where the output really is a
  product — power is force × velocity — but it is still rejected, because
  force and velocity are anti-correlated in real muscle, so summing overshoots
  the human ceiling. Where a product is the real quantity, a score already
  measures it directly. That is why **Power** exists.
- Multiple checks survive, attached to *tasks* rather than skills: roll twice
  when a task has two failure modes with different consequences.

See [Skills](../rules/skills.md).

## Each level multiplies the scores

**Decided.** One level doubles capability. Power is exponential in level.

The other option was for power to be linear in level. That would have made a
level 5000 character only twelve times a commoner. The exponential reading
makes an unlimited level track an unlimited claim about the world, which is the
purpose of having one.

**Consequences:**

- The ratio \(R\) between two characters is set by the difference in their
  levels, so the resolution table also reads as a level-difference table.
- The die stops mattering at a difference of about 8 levels at \(b=1\), or 4
  levels at \(b=2\).
- Encounter design is tightly limited. A group with more than two or three
  levels of spread cannot share opposition.
- The numbers leave physical reality quickly. Near level 200 the quantities
  exceed anything in the observable universe. Above that point the scores are
  a record of relative capability, not a claim about newtons. This is accepted,
  not solved.

See [Level](../rules/ability-scores.md#level).

## Score 1.00 is anchored to contemporary human data

**Decided.** A score of 1.00 is a median adult of today. The baselines come
from published performance data — grip dynamometry, VO₂max percentiles, simple
reaction time norms — and not from a fictional baseline tuned for play.

**Consequences:**

- Every score owes a named measurement and a citation. Four are anchored; the
  remaining fifteen are outstanding work.
- The best human is between 1.6 and 2.8 times the median, and the range differs
  per score. A common 3–18 scale would have made these ranges equal, which is
  false.
- Anything above 3.0 is outside the species, which gives "superhuman" a
  checkable meaning.
- Scores with no real instrument — Will, Projection, Composure — must name a
  proxy and admit it is a proxy.

See [Anchoring](../rules/ability-scores.md#anchor-values).

## The setting is original, not period-accurate

**Decided.** The earlier instinct toward 1320s folklore accuracy is dropped.
The setting is our own.

**Consequences:**

- The knowledge skill tree is no longer bound to a medieval curriculum. It
  should be built from what the setting actually contains rather than from
  the trivium and quadrivium.
- Alchemical signs are retained for the [aspects](../magic/aspects.md), but as
  our notation rather than as a historical claim. Nothing obliges the
  associated theory to match real alchemy.
- Technology, institutions and calendar answer to the fiction alone.
- Realism still binds *physics and bodies* — the simulationist commitment is
  to how things work, not to a particular century.

## Acuity is a scalar

**Decided.** Per-channel sensory differences moved out of the score and into
chassis offsets plus sense skills.

The original draft made Acuity a vector while every other score was a scalar,
which mixed types. Body-plan differences are properties of a species, written
once, so they belong in the chassis. Trained discrimination belongs in skills.

See [Acuity is a scalar](../rules/ability-scores.md#acuity-is-one-number).

## The four-tier bands were inverted

**Decided — a correction, not a design change.** The original cascade tested
Critical Success against \(p(\Delta + 1.585)\), which assigned about 75% of
even-odds rolls to Critical Success. Succeeding despite a 3× handicap tests
\(p(\Delta - 1.585)\).

The prose rule was always right; only the transcription was wrong. The
identity \(P(\text{CS}) = P(\text{CF}) = 1/(1+3^{b})\) holds under the
corrected form.

See [The four tiers](../rules/index.md#the-four-results).

## Aspect advantage doubles the score

**Provisional.** Advantage on the [aspect wheel](../magic/aspects.md)
multiplies the score by 2. Disadvantage divides it by 2.

Under the logarithmic scale this was written as "+1 to \(\Delta\)". It is the
same rule. The linear scale states it more directly, and no separate damage
multiplier is necessary.

Still provisional, because it depends on
[whether aspect defences are multipliers or exponents](open-questions.md#are-aspect-defences-multipliers-or-exponents).
