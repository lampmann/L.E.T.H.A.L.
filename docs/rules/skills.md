# Skills

<p class="hatnote">For the scores that skills come from, see <a href="../ability-scores/">Ability Scores</a>.</p>

<div class="infobox" markdown>

### Skills

|  |  |
|---|---|
| **Source** | Two ability scores |
| **Usual rule** | Geometric mean |
| **Limit rule** | Minimum |
| **Scale** | Same as the scores |
| **Count** | 15 |

</div>

A skill is a number that comes from two ability scores. It uses the same scale
as the scores, so a skill of 1.00 is a median adult.

## How to calculate a skill

Use one of two rules. The rule is a property of the skill.

**Geometric mean.** This is the usual rule. Multiply the two scores together.
Then take the square root.

\[ \text{skill} = \sqrt{A \times B} \]

**Minimum.** Use this rule only when one score is a hard limit. Take the lower
of the two scores.

\[ \text{skill} = \min(A, B) \]

### Examples

| Score A | Score B | Geometric mean | Minimum |
|---|---|---|---|
| 4.0 | 4.0 | 4.0 | 4.0 |
| 4.0 | 1.0 | 2.0 | 1.0 |
| 4.0 | 0.25 | 1.0 | 0.25 |
| 2.0 | 0.5 | 1.0 | 0.5 |

The geometric mean keeps the skill on the same scale as the scores. Two median
scores give a median skill.

!!! danger "Do not multiply the two scores and stop"
    Force multiplied by speed gives power, which is a different quantity in
    different units. If you need power, use the **Power** score, which measures
    it directly.

## When to make two rolls

Make one roll for one result.

Make two rolls when the task has **two different ways to fail, and the two
failures have different effects**.

- To pick a lock while a guard walks past is two rolls. To fail quietly and to
  fail loudly are different events.
- To juggle is one roll. Each way to drop the pattern drops the pattern.

## The skill list

| Skill | Scores | Use |
|---|---|---|
| **Explosive Strength** | Strength, Speed | Sprint, jump, brawl |
| **Endurance Strength** | Strength, Constitution | Climb, swim, wear armour |
| **Intimidation** | Strength, Appeal | |
| **Martial Arts** | Strength, Memory | Wrestle, martial arts |
| **Sleight of Hand** | Speed, Precision | Pick pockets, pick locks, juggle |
| **Reflex** | Speed, Perception | |
| **Technique** | Precision, Memory | Craft work |
| **Hand-Eye Coordination** | Precision, Perception | Aim, surgery, balance |
| **Vitality** | Constitution, Appeal | Appearance of health |
| **Fortitude** | Constitution, Willpower | |
| **Decorum** | Appeal, Memory | Etiquette, heraldry, story telling, acting, teaching |
| **Composure** | Appeal, Willpower | Persuade, disguise |
| **Persuasion** | Appeal, Perception | Seduce, bargain |
| **Magecraft** | Memory, Willpower | |
| **Observation** | Memory, Perception | Remember detail, search, appraise, read lips, anatomy |

<div class="stub" markdown>
Two problems are open. The list uses eight scores, but
[Ability Scores](ability-scores.md) gives nineteen. Also, **Composure** is the
name of a skill and the name of a score. Change one of the two names. See
[Design Notes](../notes/open-questions.md#which-score-list-is-correct).
</div>
