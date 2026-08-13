# Skills

<p class="hatnote">For the scores skills inherit from, see <a href="../ability-scores/">Ability Scores</a>.</p>

<div class="infobox" markdown>

### Skills

|  |  |
|---|---|
| **Structure** | Inherit from scores |
| **Default combiner** | Mean |
| **Bottleneck combiner** | Minimum |
| **Scale** | Same \(\log_2\) units |
| **Count** | 15 named |

</div>

A skill is a derived value: it inherits from ability scores, and from other
skills, and sits on the same logarithmic scale as everything else. What has to
be decided is *how* a skill combines its parents.

## The combiner is a production function

The three proposals on the table — multiple checks, minimum, and mean — are not
three unrelated ideas. They are three points on one curve, and economics has
already named it. If a skill's output is produced from two inputs, the general
form is

\[ \log \text{output} = \frac{1}{\rho}\log\!\left(w_1 x_1^{\rho} + w_2 x_2^{\rho}\right) \]

the constant-elasticity-of-substitution family. What varies is how far the
inputs substitute for each other:

| \(\rho\) | Combiner | Inputs are | Right when |
|---|---|---|---|
| \(\to -\infty\) | **Minimum** | not substitutable at all | one input is a hard gate |
| \(\to 0\) | **Mean of logs** | partially substitutable | the usual case |
| \(= 1\) | **Sum of logs** | perfectly substitutable, multiplicative | the output is literally a product |

Because our scores are already logarithms, the mean of logs *is* the geometric
mean of the underlying quantities, and the sum of logs *is* their product. The
question "which combiner is realistic" is therefore the question "how do these
two capacities actually compose in the world", and it has different answers for
different skills.

## Minimum is the wrong default

Minimum says the better attribute contributes **nothing**. For a genuine
bottleneck that is correct — no amount of Force helps you thread a needle, and
a chain does break at its weakest link.

For most pairs it is plainly false. Take Explosive Strength, which inherits
from Strength and Speed. Under minimum, a character at Strength +2 / Speed 0
is identical to one at 0 / 0. They are not: they are four times stronger, and
that shows up in every explosive movement they make. The information is real
and minimum discards it.

!!! danger "The 'never add scores' rule has one genuine exception"
    [Ability Scores](ability-scores.md#combining-scores) warns that adding logs
    multiplies quantities. That warning stands as a default, but the reason it
    is a warning rather than a law is worth stating: sometimes multiplying is
    exactly right.

    Mechanical power *is* force × velocity. In log space that is
    \(\log P = \log F + \log v\) — a literal sum of the two scores. So for that
    one skill, addition is the physics.

    It still should not be used, and the reason is instructive. Force and
    velocity are **anti-correlated** in real muscle: the force–velocity curve
    means nobody maximises both at once. Adding assumes independence, so it
    overshoots — it would place a merely elite athlete at +2 Power when
    measurement puts the human ceiling at about +1.46. Where a product really
    is the quantity of interest, the system already has a score that measures
    it directly. That is precisely why **Power** exists as its own score
    instead of being derived from Force and Speed.

## The rule

**Mean by default. Minimum where the fiction has a hard gate, marked on the
skill. Never sum.**

The mean is the only combiner that keeps a skill on the same scale as its
parents, which matters because difficulties are anchored to real human
quantities. A character with both parents at +1 has the skill at +1, and that
number means the same thing everywhere in the book.

### What about multiple checks?

Rolling one check per parent — the Vermahn–Goldwynn reading — is the most
honest model of *compound failure*, and it should not be dismissed. Juggling
really can fail from mistiming or from misplacement, independently, and
independent failure modes multiply.

But it is the wrong tool here, for two reasons. It is strictly harsher than
minimum at every \(b\), so it silently makes every multi-parent skill harder
than a single-parent one of the same value. And it doubles the roll count in a
system that already has continuous initiative and per-location wounds.

The case it models well is real, so keep it — but attach it to *tasks*, not to
skills:

> Roll twice when a task has two separable failure modes **with different
> consequences**. Roll once when it has one outcome.

Picking a lock while a guard patrols is two checks because failing quietly and
failing loudly are different events. Juggling is one check, because every way
of dropping the pattern drops the pattern.

## The skill list

Skills are named pairs of ability scores. The full pairing of eight scores
gives 28 candidates; these fifteen were selected as the ones that carry weight.

| Skill | Inherits from | Covers |
|---|---|---|
| **Explosive Strength** | Strength + Speed | Sprint, jump, brawling |
| **Endurance Strength** | Strength + Constitution | Climb, swim, bearing armour |
| **Intimidation** | Strength + Appeal | |
| **Martial Arts** | Strength + Memory | Wrestling, martial arts |
| **Sleight of Hand** | Speed + Precision | Pickpocketing, lockpicking, juggling |
| **Reflex** | Speed + Perception | |
| **Technique** | Precision + Memory | Craftsmanship, artisanry |
| **Hand-Eye Coordination** | Precision + Perception | Aim, surgery, balance |
| **Vitality** | Constitution + Appeal | Health as it presents |
| **Fortitude** | Constitution + Willpower | |
| **Decorum** | Appeal + Memory | Etiquette, heraldry, storytelling, acting, teaching |
| **Composure** | Appeal + Willpower | Persuasion, disguise |
| **Persuasion** | Appeal + Perception | Seduction, haggling |
| **Magecraft** | Memory + Willpower | |
| **Observation** | Memory + Perception | Remember detail, search, appraise, read lips, symbology, anatomy |

<div class="stub" markdown>
Which of these are **gated** rather than averaged needs marking. Hand-Eye
Coordination is the clearest candidate for minimum — no amount of Perception
rescues a shaking hand. Most of the rest look like genuine averages.
</div>

## The two score lists disagree

!!! warning "Unresolved conflict"
    This list pairs **eight** scores — Strength, Speed, Precision,
    Constitution, Appeal, Memory, Willpower, Perception. The
    [Ability Scores](ability-scores.md) page defines **nineteen**. Both cannot
    be canonical.

    Pairing nineteen scores is not an option: it gives 171 combinations. But
    the generative rule was only ever a way to enumerate candidates, not a law
    — so the fix is to keep these fifteen names and re-parent them onto the
    nineteen, several of which absorb a pair outright:

    - **Explosive Strength** → Power, which already *is* force × velocity
    - **Endurance Strength** → Stamina and Force
    - **Reflex** → Latency and Acuity
    - **Hand-Eye Coordination** → Precision and Acuity
    - **Fortitude** → Homeostasis and Will
    - **Composure** → the Composure score directly

    Note the collision: Composure is currently both a skill (Appeal +
    Willpower) and an ability score, and the \(b\) rule
    [uses the score](index.md#the-character-term). One of them needs renaming.

    Tracked in [Open Questions](../design/open-questions.md#which-score-list-is-canonical).
