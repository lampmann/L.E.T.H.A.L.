# Ability Scores

<p class="hatnote">For the rule that uses these scores, see <a href="../">Core Resolution</a>. For the rule language, see <a href="../ace/">Rule Language</a>.</p>

<div class="infobox" markdown>

### Ability Scores

|  |  |
|---|---|
| **Scale** | Linear |
| **Median adult** | 1.00 |
| **Human range** | 0.35 to 2.8 |
| **Minimum** | Above zero |
| **Maximum** | None |
| **Count** | 19 |

</div>

## The rule

```
Every ability-score is a number that is greater than 0.
No ability-score has a maximum.
Every ability-score measures exactly 1 quantity.

If a creature has an ability-score X and X measures a quantity Q and a median-adult has a quantity M then X = Q / M.

If an ability-score measures a quantity that is better when the quantity is small then the ability-score measures a reciprocal of the quantity.

If a creature has a level L and has an ability-score X and X has a base-value Z then X = Z * 2^L.

Every chassis has a mass and has a length and has a density and has an energy-use and has a limb-count and has a lifespan.
No chassis-value is an ability-score.

If a creature makes a check for a sense and the creature has an acuity A and the creature has a chassis-factor G for the sense and the creature has a skill K for the sense then the check has a score S and S = A * G * K.
```

The rest of this page explains those sentences.

## The scale

A score is a measured quantity, divided by the quantity for a median adult
human.

- **1.00** is a median adult.
- **2.00** is twice the quantity.
- **0.50** is half the quantity.
- There is no maximum. The minimum is a number above zero.

Where a small number is better, such as reaction time, the score is the median
value divided by the measured value. A higher score is thus always better.

## Why the scale is linear

The scores are the quantities themselves. A score of 4.0 is four times a score
of 1.0, in newtons or in watts or in millilitres of oxygen.

The [resolution rule](index.md) uses the ratio \(S/D\), so no conversion is
necessary at any point. You divide two numbers that are already in the correct
units.

The human range is not the same for each score. This is correct. Real abilities
do not vary by equal quantities.

## The scores

### Output

| Score | Measured quantity |
|---|---|
| **Force** | Maximum force, in newtons. |
| **Power** | Maximum mechanical power, in watts. Force multiplied by speed. |
| **Stamina** | Maximum oxygen use, and the part of maximum output that the body can hold. |
| **Recovery** | Speed of repair: wounds, immune response, training effect. |

### Integrity

| Score | Measured quantity |
|---|---|
| **Toughness** | Mechanical energy that the body absorbs before tissue breaks. |
| **Homeostasis** | Resistance to poison, heat, cold, low oxygen, pressure and loss of water. |

### Control

| Score | Measured quantity |
|---|---|
| **Precision** | Accuracy of small movements. The reciprocal of position error. |
| **Agility** | Whole-body balance, and speed of correction. |
| **Articulation** | Range of movement of the joints. Also holds limb layout for bodies that are not human. |

### Signal

| Score | Measured quantity |
|---|---|
| **Acuity** | Sensitivity of the senses. |
| **Latency** | The reciprocal of loop time from sense to movement. A median adult is near 250 ms. |
| **Tempo** | Decision cycles each second. This controls how many actions occur in a given time. |

### Mind

| Score | Measured quantity |
|---|---|
| **Memory** | Accuracy of storage, capacity, and reliability of recall. |
| **Attention** | Number of objects held at one time, and length of watch. |
| **Composure** | Resistance to sudden stress: fear, pain, shock, surprise. |
| **Will** | Resistance to long stress: force, loss, temptation, tiredness. |
| **Plasticity** | Speed of learning. This sets how quickly skills increase with practice. |
| **Affect Reading** | Accuracy at finding the feelings and the intentions of other persons. |
| **Projection** | Output: strength and control of the voice, clarity of signal, appearance. |

## Acuity is one number

An early draft made Acuity a vector, with one value for each sense. All other
scores were single numbers. This mixed two different types.

Acuity is now one number: general sensitivity of the senses.

Differences between the senses belong in two other places:

- **The chassis** holds a factor for each channel, because these belong to a
  body type and not to an individual. An eagle has a factor of 64 for day
  vision. A bloodhound has a factor of 2000 for smell. All human factors are
  1.0.
- **Skills** hold trained ability: Sight, Hearing, Smell, Taste and Touch.

A check against one sense uses:

\[ \text{channel} = \text{Acuity} \times \text{chassis factor} \times \text{skill} \]

## Chassis

The chassis is not a set of scores. It is a set of measurements in real units:

**Mass, length, density, resting energy use, number of limbs, lifespan, and a
factor for each sense channel.**

Use the square-cube law to find the effect of mass and length on Force,
Toughness and Stamina. This is what makes a dragon different from a human with
large numbers.

## How to combine scores

!!! danger "Do not multiply two scores together"
    Two scores multiplied together give a quantity in different units. A
    character with Force 4.0 and Precision 0.25 is not equal to a character
    with 1.0 and 1.0. The first character is four times stronger and four times
    less accurate.

Two rules are sufficient:

**The minimum, for a hard limit.** To put thread through a needle needs
Precision only. No quantity of Force helps.

**The geometric mean, when two abilities exchange.** Multiply the two scores
together, then take the square root. Two scores of 4.0 give a skill of 4.0. A
score of 4.0 and a score of 1.0 give a skill of 2.0.

The correct rule is a property of the task. Write it in the task, not on the
character sheet.

## Why there is no Intelligence score

You cannot play a character who is more intelligent than you are. A score for
intelligence gives a number that the player cannot use.

The parts of thought that dice can control are already present: **Memory,
Attention, Tempo and Plasticity**. What is left is insight, and the player must
supply it.

**Affect Reading** and **Projection** have the same problem, but they stay for
a different reason. The referee can speak their result. *"He is lying, and he
is afraid"* is a sentence that the referee can say. *"You find the correct
answer"* is not.

## Anchor values

Score 1.00 is a median adult of today. These four scores have measured anchors:

| Score | Measured as | Median adult (1.00) | Best human |
|---|---|---|---|
| **Force** | Grip dynamometer | 35 kgf | 2.6 |
| **Power** | Maximum anaerobic power | 800 W | 2.8 |
| **Stamina** | Maximum oxygen use | 40 ml/kg/min | 2.1 |
| **Latency** | Simple visual reaction time | 250 ms | 1.6 |

The best human is between 1.6 and 2.8 times the median. The range is not the
same for each score. A common scale of 3 to 18 would make these ranges equal,
which is not correct.

A score of more than 3.0 is thus outside the human species.

### Scores with weak data

Force, Power, Stamina and Latency have good instruments. The other scores do
not. A system that models reality must say which is which.

- **Good instruments.** Force, Power, Stamina, Recovery, Latency, Precision,
  Toughness.
- **Measurable, with difficulty.** Agility, Articulation, Homeostasis,
  Attention, Memory.
- **Substitute measure only.** Tempo, Composure, Will, Plasticity, Affect
  Reading, Projection. Each needs a named substitute measurement, and a note
  that says the substitute is not the ability.

Sources: [grip norms](https://www.jospt.org/doi/10.2519/jospt.2018.7851),
[international grip data](https://www.sciencedirect.com/science/article/pii/S2095254624001741),
[oxygen use percentiles](https://fitnessnorms.com/cardio/vo-2-max/),
[reaction time norms](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7413367/).

<div class="stub" markdown>
Fifteen scores still have no anchor. Each one needs a measurement, a median
value and a source. All difficulty tables wait for this work.
</div>

## Level

Each level multiplies the scores. The scores are linear in the quantity, and
the quantity increases by a constant factor at each level.

| Levels above | Score becomes |
|---|---|
| 1 | 2 times |
| 3 | 8 times |
| 5 | 32 times |
| 10 | 1024 times |
| 20 | 1 million times |

There is no maximum level. Level 5000 is a statement about the world, and the
scale accepts it.

### Effect on play

The ratio \(R\) between two characters is set by the difference in their
levels. The [resolution table](index.md#the-skill-factor) thus also works as a
table of level differences.

| Level difference | \(R\) | b = 1 | b = 2 |
|---|---|---|---|
| 1 | 2 | 67% | 80% |
| 2 | 4 | 80% | 94% |
| 3 | 8 | 89% | 98% |

Above a difference of 8 levels at \(b = 1\), or 4 levels at \(b = 2\), the die
cannot change the result. This shows when a character is fully outside the
class of the opposition.

Keep the levels in one group close together. A group with a difference of five
levels cannot use the same opposition.

<div class="stub" markdown>
Open: does one level give one increase to one score, or a quantity of increase
to divide between the scores?
</div>
