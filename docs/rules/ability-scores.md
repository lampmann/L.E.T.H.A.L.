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

<div class="stub" markdown>
Still open: whether scores are anchored to published human performance data
(grip dynamometry, VO₂max distributions, simple reaction time norms) or to a
fictional baseline set by hand. This changes every table in the book and is
tracked in [Open Questions](../design/open-questions.md#what-anchors-the-baseline).
</div>
