# Skills

<p class="hatnote">For the scores that skills come from, see <a href="../ability-scores/">Ability Scores</a>. For the rule language, see <a href="../ace/">Rule Language</a>.</p>

<div class="infobox" markdown>

### Skills

|  |  |
|---|---|
| **Source** | Ability scores |
| **Usual rule** | Geometric mean |
| **Limit rule** | Minimum |
| **Scale** | Same as the scores |
| **List** | Not written |

</div>

A skill is a number that comes from ability scores. It uses the same scale as
the scores. A skill of 1.00 is a median adult.

## The rule

```
Every skill derives-from at least 1 ability-score.
Every skill uses a mean-rule or uses a minimum-rule.

If a skill uses a mean-rule and derives-from an ability-score A and derives-from an ability-score C then the skill has a value V and V = (A * C)^0.5.

If a skill uses a minimum-rule and derives-from an ability-score A and derives-from an ability-score C and A =< C then the skill has a value V and V = A.

If a skill uses a minimum-rule and derives-from an ability-score A and derives-from an ability-score C and C < A then the skill has a value V and V = C.

Every skill that has a hard-limit uses a minimum-rule.
Every skill that has no hard-limit uses a mean-rule.

If a task has 2 failure-modes that have different effects then a player makes 2 checks for the task.
If a task has exactly 1 outcome then a player makes exactly 1 check for the task.
```

The rest of this page explains those sentences.

## How to calculate a skill

**Geometric mean.** This is the usual rule. Multiply the scores together. Then
take the root.

\[ \text{skill} = \sqrt{A \times B} \]

**Minimum.** Use this rule only when one score is a hard limit. Take the lowest
score.

### Examples

| Score A | Score B | Geometric mean | Minimum |
|---|---|---|---|
| 4.0 | 4.0 | 4.0 | 4.0 |
| 4.0 | 1.0 | 2.0 | 1.0 |
| 4.0 | 0.25 | 1.0 | 0.25 |
| 2.0 | 0.5 | 1.0 | 0.5 |

The geometric mean keeps the skill on the same scale as the scores. Two median
scores give a median skill.

!!! danger "Do not multiply the scores and stop"
    Force multiplied by speed gives power. Power is a different quantity in
    different units. If you need power, use the **Power** score. It measures
    power directly.

## When to make two rolls

Make one roll for one result.

Make two rolls when a task has **two different ways to fail, and the two
failures have different effects**.

- To pick a lock while a guard walks past is two rolls. To fail quietly and to
  fail loudly are different events.
- To juggle is one roll. Each way to drop the pattern drops the pattern.

## The skill list

<div class="stub" markdown>
**There is no skill list yet.**

An earlier list made a skill from each pair of eight ability scores. That list
is dead. The wiki now uses
[nineteen ability scores](ability-scores.md#the-scores), and the pair rule
gives 171 combinations at that size.

Build the new list from activities, not from pairs of scores. A skill names a
thing a person does. Then find which scores it needs.

Two constraints are settled:

1. A skill is an activity. Combat skills sit at the same level as
   investigation and as recall of knowledge. Combat gets no special treatment.
2. No skill may take the name of an ability score. The old Composure skill is
   removed, because Composure is a score.

A first proposal is in the [Scratchpad](../notes/scratchpad.md#skill-list-proposal).
It is a proposal. It is not decided.
</div>
