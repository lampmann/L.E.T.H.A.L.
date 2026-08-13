# Decisions

A record of settled design calls: what was decided, why, and what it forecloses.
Open items live in [Open Questions](open-questions.md).

Each entry stays here permanently. When a decision is reversed, the entry is
amended rather than deleted — knowing what was tried and rejected is worth more
than a tidy list.

## Scores are linear in level; power is exponential

**Decided.** One level is one point is one doubling of real capability.

The alternative — power linear in level, scores as \(\log_2(\text{level})\) —
would have compressed level 5000 into about twelve points above a commoner.
Taking the exponential reading instead means an unbounded level track makes an
unbounded claim about the world, which is the point of having one.

**Consequences:**

- \(\Delta\) between two characters is exactly their level gap, so the
  [resolution table](../rules/index.md) reads directly as a level-difference
  table.
- Dice stop mattering at a gap of \(7.64 / b\) levels. At \(b = 2\) that is
  four levels.
- Encounter design is tightly constrained. A party spanning more than two or
  three levels cannot share opposition meaningfully.
- Numbers leave physical reality quickly. Around +200 the quantities exceed
  anything in the observable universe, so at high level the scores are
  bookkeeping about relative capability rather than claims about newtons. This
  is accepted, not solved.

See [Level and scaling](../rules/ability-scores.md#level-and-scaling).

## Score 0 is anchored to contemporary human data

**Decided.** Baselines come from published present-day performance
distributions — handgrip dynamometry, VO₂max percentiles, simple reaction time
norms — not from a fictional baseline tuned for play.

**Consequences:**

- Every score owes a named measurement and a citation. Four are anchored; the
  remaining fifteen are outstanding work.
- The human range lands around ±1.5 on most scores, and differs per score by a
  factor of two or more. This is the payoff: the log scale preserves the
  difference instead of flattening it.
- Anything past +2 is outside the species, which gives the superhuman range a
  hard, checkable meaning.
- Scores with no real instrument — Will, Projection, Composure — must name a
  proxy and admit it is a proxy.

See [Anchoring](../rules/ability-scores.md#anchoring).

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

See [Acuity is a scalar](../rules/ability-scores.md#acuity-is-a-scalar).

## The four-tier bands were inverted

**Decided — a correction, not a design change.** The original cascade tested
Critical Success against \(p(\Delta + 1.585)\), which assigned about 75% of
even-odds rolls to Critical Success. Succeeding despite a 3× handicap tests
\(p(\Delta - 1.585)\).

The prose rule was always right; only the transcription was wrong. The
identity \(P(\text{CS}) = P(\text{CF}) = 1/(1+3^{b})\) holds under the
corrected form.

See [The four tiers](../rules/index.md#the-four-tiers).

## Aspect advantage is ±1 to Δ

**Provisional.** Advantage on the [aspect wheel](../magic/aspects.md) reads as
one doubling rather than as a separate damage multiplier, so the matchup matrix
and the resolution table speak the same units.

Marked provisional because it depends on
[whether mixed aspects combine in linear or log space](open-questions.md#aspects-in-linear-or-log-space).
