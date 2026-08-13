# Aspects

<p class="hatnote">For the operators that act on aspects, see <a href="../notation/">Spell Notation</a>.</p>

<div class="infobox" markdown>

### Aspects

|  |  |
|---|---|
| **Count** | 5 or 7. Not decided. |
| **Named** | 5 |
| **Vector** | 5 values. Total is 1. |
| **Advantage** | Multiply the score by 2 |
| **Disadvantage** | Divide the score by 2 |

</div>

Magic has a number of aspects. Each aspect has several **manifestations**: a
classical element, a database operation, and a domain. These are not different
systems. They are the same aspect, seen from different sides.

The number of aspects is a root of \(x^2 - 12x + 35 = 0\). Thus it is five or
seven. This is not decided.

## The five aspects

| # | Aspect | Element | Operation | Domain |
|---|---|---|---|---|
| 0 | **Hylogenesis** | Earth | Create | Matter |
| 1 | **Anabiosis** | Water | Update | Life |
| 2 | **Pyrolysis** | Fire | Delete | Energy |
| 3 | **Autophoresis** | Air | Move | *Not decided* |
| 4 | **Anamnesis** | Aether | Read | Spells that act on spells |

Two more aspects, ⟨Aspect ζ⟩ and ⟨Aspect η⟩, are placeholders. Use them if the
count becomes seven.

<div class="stub" markdown>
Light has no aspect yet. Pyrolysis and Anamnesis both claim it. Give it to one
of the two.
</div>

## The cycle

For any aspect \(N\), count forward around the wheel:

- \(N\) **has advantage against** \(N+1\) and \(N+2\).
- \(N\) **has disadvantage against** \(N-1\) and \(N-2\).
- All other pairs are equal.

With five aspects, each aspect has advantage against two and disadvantage
against two. No pair is equal. Every combination of aspects has a result.

### Matchup table

The row acts on the column.

| Attacker | Hylogenesis | Anabiosis | Pyrolysis | Autophoresis | Anamnesis |
|---|---|---|---|---|---|
| **Hylogenesis** | — | ×2 | ×2 | ÷2 | ÷2 |
| **Anabiosis** | ÷2 | — | ×2 | ×2 | ÷2 |
| **Pyrolysis** | ÷2 | ÷2 | — | ×2 | ×2 |
| **Autophoresis** | ×2 | ÷2 | ÷2 | — | ×2 |
| **Anamnesis** | ×2 | ×2 | ÷2 | ÷2 | — |

## How to use advantage

Advantage multiplies your score by 2. Disadvantage divides your score by 2.

Use the new score in the [resolution formula](../rules/index.md). No other
calculation is necessary.

## Mixed aspects

A spell can use more than one aspect. Write the parts as a list of five values.
Each value is between 0 and 1. The total of the five values is 1.

Water is approximately \([0, 1, 0, 0, 0]\).

Each entity also has a list of five defence values. To find the effect against
a target, multiply each spell value by the matching defence value, then add the
five results.

<div class="stub" markdown>
Not decided: whether the defence values are multipliers or exponents. The two
give different results for a spell that uses more than one aspect.
</div>

## Theory

⟨Character III⟩ published four papers. They prove, in order:

1. A function \(A(x)\) exists, where \(x\) is a mathematical object. It gives
   the aspect list necessary to create that object.
2. \(A(x)\) has a value for every mathematical object in ZFC.
3. \(\forall \epsilon > 0:\ \lim_{n \to \infty} P\left(1-\epsilon > \max A(x) > \tfrac{1}{5}+\epsilon \;\middle|\; K(x)=n\right) = 0\),
   where \(K\) is Kolmogorov complexity.
4. \(\forall x, y:\ A(x) = A(y) \implies K(x) = K(y)\)

The third result is important in play. As objects become more complex, their
aspect lists stop being mixed. In the limit, an object is either equal in all
five aspects, or almost fully one aspect. The middle becomes empty.

The fourth result is stronger. The aspect list gives the complexity. Two
objects with the same aspect list have the same complexity.

Each paper ends with *"Ceterum censeo bears are fish."*

## Notes

For the argument about five aspects against seven, and for the conflict between
aspects and verbs, see [Design Notes](../notes/open-questions.md).
