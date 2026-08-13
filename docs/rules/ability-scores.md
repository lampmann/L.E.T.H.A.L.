# Ability Scores

<p class="hatnote">For how scores resolve into outcomes, see <a href="../">Core Resolution</a>.</p>

<div class="infobox" markdown>

### Ability Scores

|  |  |
|---|---|
| **Scale** | \(\log_2\) of a measured quantity |
| **Baseline** | 0 = median adult human |
| **Step** | +1 = twice the quantity |
| **Range** | Unbounded both ways |
| **Count** | 19 scores + chassis |
| **Intelligence** | Deliberately absent |

</div>

Every score is the base-2 logarithm of a real, measured quantity, relative to
the median adult human.

- **0** — median human
- **+1** — twice the quantity
- **−1** — half the quantity
- No ceiling, no floor

For quantities where lower is better — reaction time, positional error — the
score is defined as \(\log_2(\text{baseline} \div \text{measured})\), so higher
always means better.

## Why logarithms

Infinite scaling comes for free, and the scores drop straight into the
[resolution curve](index.md) as a subtraction. More importantly, the human
range differs per score — roughly ±1.5 for Force, but only about ±0.6 for
Latency — and that is *correct*. Real traits do not vary by equal amounts, and
a simulationist system must not flatten them into a common 3–18.

## The scores

### Output

| Score | Measures |
|---|---|
| **Force** | Peak force the body applies, in newtons. |
| **Power** | Peak mechanical power, in watts. Splits from Force because force × velocity dissociates — a powerlifter and a sprinter differ here. |
| **Stamina** | Aerobic ceiling, and the fraction of peak output sustainable over time. |
| **Recovery** | Rate of repair: wound healing, immune response, training adaptation. |

### Integrity

| Score | Measures |
|---|---|
| **Toughness** | Mechanical energy absorbed before tissue fails. |
| **Homeostasis** | Resistance to poison, heat, cold, hypoxia, pressure, dehydration. Chemical and thermal rather than mechanical, so it is a separate system from Toughness. |

### Control

| Score | Measures |
|---|---|
| **Precision** | Fine-motor accuracy. Inverse of positional error in millimetres. |
| **Agility** | Whole-body dynamic balance and correction rate. |
| **Articulation** | Joint range of motion. Carries limb topology for non-human bodies. |

### Signal

| Score | Measures |
|---|---|
| **Acuity** | Overall sensory gain relative to the median human. See [below](#acuity-is-a-scalar) — this differs from the original draft. |
| **Latency** | Inverse of sensorimotor loop time. Human ≈ 200 ms; a score of +7 gives 1.5 ms. |
| **Tempo** | Decision cycles per second. Subjective time dilation, and it governs actions per unit of clock time. |

### Mind

| Score | Measures |
|---|---|
| **Memory** | Encoding fidelity, capacity, recall reliability. |
| **Attention** | Objects tracked simultaneously, and vigilance duration. |
| **Composure** | Acute stress: fear, pain, shock, surprise. |
| **Will** | Sustained load: coercion, deprivation, temptation, exhaustion. |
| **Plasticity** | Learning rate. Sets how fast skills rise per hour of practice. |
| **Affect Reading** | Accuracy at detecting emotional and intent states in others. |
| **Projection** | Expressive output: vocal power and control, signal clarity, appearance. |

## Acuity is a scalar

The original draft made Acuity a *vector* — one entry per sensory channel —
while every other score was a scalar. That mixes types, and it is the one part
of the draft flagged for revision.

The fix keeps what the vector was protecting. An eagle, a bat and a bloodhound
genuinely are not "high perception" in the same way, and that distinction must
survive. It moves to a layer that already exists:

**Acuity stays a single score** — overall sensory gain, in the same
\(\log_2\) units as everything else.

**Per-channel differences live in the chassis** as offsets, because they are
properties of a body plan rather than of an individual. A generic eagle carries
`photopic +6`, a bat `hearing +4, echolocation +8`, a bloodhound
`olfaction +11`. A human's offsets are all zero by definition.

**Trained discrimination lives in skills** — Sight, Hearing, Smell, Taste,
Touch — which is where the existing skill list already puts them.

A check against one channel therefore reads:

\[ \text{channel score} = \text{Acuity} + \text{chassis offset} + \text{skill} \]

Nothing is lost, the type error is gone, and it reuses the two structures the
system already has rather than inventing a third. Species offsets get written
once per body plan and never again, which is exactly the property that made
them a bad fit for a per-character score.

!!! note "Exotic channels"
    Echolocation, electroreception and magnetoreception are chassis entries
    with no human baseline. Give them an absolute reference in their own units
    rather than a relative offset, since \(\log_2\) of a ratio to zero is
    undefined.

## Chassis

Not scores. Raw parameters, recorded in real units:

**Mass, length, density, basal metabolic rate, limb count, lifespan, sensory
channel offsets.**

Apply the square-cube law to derive modifiers to Force, Toughness and Stamina
from mass and length. This is what makes a dragon a dragon rather than a human
with big numbers — the scaling laws do the work, and you are not hand-waving a
+40 Force onto something the size of a barn.

## Combining scores

!!! danger "Never add two scores together"
    Adding logarithms multiplies the underlying quantities. A character with
    Force +6 and Precision −6 is emphatically not equivalent to one at 0 and 0
    — they are a thousand times stronger and a thousand times clumsier.
    Summing the two produces 0 and asserts a mediocrity that is nowhere in the
    fiction.

Two combination rules cover the cases:

**Minimum, for bottlenecks.** Threading a needle is gated by Precision alone.
No amount of Force fixes it. This matches the Stahlmann–Greenberg reading of
skill inheritance, and it should be the default.

**Mean, for genuine trade-offs.** Where two capacities really do substitute for
one another at the margin — hauling a load either quickly or in more trips —
average the contributing scores.

Which rule applies is a property of the task and belongs in the task's
description, not the character sheet.

## Why there is no Intelligence

You cannot roleplay a character more intelligent than you are, so a score
claiming to measure it produces a number the player cannot cash.

Removing it does not remove the tractable parts of cognition. **Memory,
Attention, Tempo and Plasticity** absorb everything about thinking that dice
can adjudicate. What is left over is insight, and insight is precisely the part
the player must supply.

The same objection technically applies to **Affect Reading** and
**Projection** — you cannot roleplay more perceptive or more compelling than
you are either. They survive on a different test: their outputs are describable
by the referee. *"He is lying, and he is frightened"* is a statement the GM can
make. *"You deduce the correct answer"* is not.

## Relation to the earlier stat lists

The brainstorm worked through several groupings — FATAL's, the
Bach–Deutschemann Conjecture, the Weiss–Bronzestein Procedure, Aristotle's
tripartite soul. This list supersedes them, but the mapping is mostly clean:

| Earlier name | Here |
|---|---|
| Strength | Force, Power |
| Speed | Latency (reaction), Power (movement) |
| Precision | Precision |
| Constitution | Toughness, Homeostasis, Stamina |
| Memory | Memory |
| Willpower | Will, Composure |
| Appeal | Projection |
| Perception | Acuity + chassis offsets |
| Knowledge | *Not a score* — invest in knowledge skills instead |

Dropping Knowledge as a score follows the brainstorm's own conclusion: a
knowledge stat makes far less sense than putting points into knowledge skills
directly.

## Anchoring

**Settled: score 0 is anchored to contemporary human performance data**, not to
a baseline set by hand. Every score should ultimately name a measurement and a
published distribution, so that a number on a sheet can be checked against the
world.

| Score | Measured as | Median adult (0) | Elite human | Δ |
|---|---|---|---|---|
| **Force** | Handgrip dynamometry | ≈ 35 kgf (343 N) | ≈ 90 kgf | +1.36 |
| **Power** | Peak anaerobic power | ≈ 800 W | ≈ 2200 W | +1.46 |
| **Stamina** | VO₂max | ≈ 40 ml/kg/min | ≈ 85 ml/kg/min | +1.09 |
| **Latency** | Simple visual reaction time | ≈ 250 ms | ≈ 160 ms | +0.64 |

!!! note "The data confirms the reason for using logarithms"
    These four ranges are *not the same width*, and that is the whole argument
    for the scale. The gap between a median adult and the best human alive is
    about 1.4 points of Force but only 0.6 points of Latency. A system that
    forced both into a common 3–18 would be claiming, falsely, that elite
    reflexes are as far from average as elite strength is. Here the difference
    is simply recorded.

    It also means **everything human fits in roughly ±1.5**. Any score past +2
    is already outside the species, which is exactly the property that makes
    the superhuman range meaningful rather than decorative.

### Where the data is thin

Force, Power, Stamina and Latency have excellent instrumentation. Others do
not, and a simulationist system should be honest about which is which:

- **Well instrumented.** Force, Power, Stamina, Recovery, Latency, Precision,
  Toughness — all have standard laboratory measures.
- **Measurable, with caveats.** Agility, Articulation (goniometry),
  Homeostasis, Attention, Memory. Real instruments exist but no single number
  summarises them.
- **Proxy only.** Tempo, Composure, Will, Plasticity, Affect Reading,
  Projection. These need a named proxy measurement and an honest note that the
  proxy is not the thing. Where no proxy exists, the score is a fictional
  baseline wearing a lab coat, and the page should say so.

Sources for the anchors above: [handgrip norms](https://www.jospt.org/doi/10.2519/jospt.2018.7851),
[international grip data](https://www.sciencedirect.com/science/article/pii/S2095254624001741),
[VO₂max percentiles](https://fitnessnorms.com/cardio/vo-2-max/),
[reaction time norms](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7413367/).

<div class="stub" markdown>
Needs filling in: the remaining fifteen scores, each with a named measurement,
a median, and a citation. This is the single largest piece of unglamorous work
left in the system, and every difficulty table depends on it.
</div>

## Level and scaling

**Settled: scores rise linearly with level, so real capability is exponential
in level.** One level is one point is one doubling.

| Level gap | Capability ratio |
|---|---|
| 1 | 2× |
| 3 | 8× |
| 5 | 32× |
| 10 | 1,024× |
| 20 | ~1,000,000× |

This is what makes unbounded levels mean something. Level 5000 is not a large
number on a sheet; it is a claim about the world, and the scale takes it
literally.

### What that does to play

Since \(\Delta\) between characters is just their level gap, the
[resolution curve](index.md) turns level differences straight into odds:

| Level gap | b = 0.5 | b = 1 | b = 2 | b = 4 |
|---|---|---|---|---|
| **1** | 58.6% | 66.7% | 80.0% | 94.1% |
| **Dice stop mattering at** | 15 | 8 | 4 | 2 |

The second row is the important one. Because d100 caps the swing at ±7.64, a
gap of \(7.64 / b\) levels makes the roll irrelevant — the outcome is decided
before the die is picked up.

That is a feature: it defines *out of your league* numerically, and it tells a
referee when to stop rolling and narrate. But it constrains encounter design
hard. At \(b = 2\), a four-level gap is already deterministic, so a party
spanning five levels cannot meaningfully face the same opposition. Parties
should stay within a couple of levels of each other, and the interesting range
of opposition is narrow and moves with them.

<div class="stub" markdown>
Open: whether a level grants one point to one score, or a budget spread across
several. One-point-per-level keeps the level gap and \(\Delta\) identical,
which is what makes the table above exact. A budget breaks that identity and
makes characters of equal level genuinely different, at the cost of the clean
arithmetic.
</div>
