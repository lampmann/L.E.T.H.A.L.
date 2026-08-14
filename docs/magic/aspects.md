# Aspects

<p class="hatnote">For the operators that act on aspects, see <a href="../notation/">Spell Notation</a>.</p>

<div class="infobox" markdown>

### Aspects

|  |  |
|---|---|
| **Count** | 5 or 7. Not decided. |
| **Named** | 5 |
| **Vector** | 5 values. Total is 1. |
| **Verbs** | Separate symbols. Correlated. |
| **Pure vectors** | 5. One complexity each. |
| **Matchups** | Not decided |

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

## Verbs and aspects are correlated

A verb and an aspect use **different symbols**. A caster writes both. The verb
column in [Spell Notation](notation.md) stays.

The two are not independent. Each verb has an aspect. Create has Hylogenesis.
Delete has Pyrolysis. When a caster writes a verb, that verb puts its aspect
into the spell.

So the aspect list of a spell comes from the whole expression. The verbs add to
it. The targets add to it. A caster does not write the list. The list follows
from what the caster writes.

### Example

A firebolt creates fire. A caster writes the Create verb and the Fire aspect.

- The Fire target gives Pyrolysis.
- The Create verb gives a small part of Hylogenesis.

The result is a mix, and the mix is very unequal:

\[ [0.01,\; 0,\; 0.99,\; 0,\; 0] \]

A firebolt is thus not pure Pyrolysis. It is almost pure Pyrolysis.

### Why no spell is exactly pure

The fourth theorem states that the aspect list gives the complexity:

\[ A(x) = A(y) \implies K(x) = K(y) \]

Take two objects that are both pure Pyrolysis. Their aspect lists are equal.
Therefore their complexities are equal.

**Every pure aspect has exactly one complexity.** If a pure Pyrolysis object of
231 bits exists, then each pure Pyrolysis object has 231 bits. There is no
range. There is one value.

Now apply the reverse. A firebolt has some complexity. That complexity is
almost certainly not exactly the pure value. Therefore a firebolt is not pure
Pyrolysis, and the verb explains why: the Create verb adds Hylogenesis.

This agrees with the third theorem. That theorem says a complex object has a
largest aspect value near 1, or has five equal values. A largest value of 0.99
is in the first group.

### Results of this rule

**The notation is unchanged.** Verbs, handles, metaprogramming operators,
modifiers and predicates all stay. The five verbs and the five aspects remain
two symbol sets, and 35 verb-aspect pairs remain available.

**The list of pure spells is short.** There are exactly five pure aspect lists,
one for each aspect. Each one has exactly one complexity. A pure spell is
therefore a unique thing, and not a class of things. A pure spell also cannot
use a verb of a different aspect.

**The aspect list gives the complexity of a spell.** Two spells with the same
aspect list have the same complexity. A designer who wants two spells of
different complexity must give them different aspect lists.

<div class="stub" markdown>
The rule that gives the numbers is not written. A firebolt is approximately 99
percent Pyrolysis, but nothing produces that value yet.

It is also not decided whether the correlation does anything **other** than set
the percentages. It can be only a weight on the aspect list. It can also make
some verb and aspect pairs cheaper or harder than others.
</div>

## Matchups

<div class="stub" markdown>
**Two questions are open, and the second depends on the first.**

1. Do matchups exist at all? An aspect can have an advantage against another
   aspect, or all aspects can be equal.
2. Are there five aspects or seven?

The text below is a proposal. It is not a rule. Do not use it in play yet.
</div>

### If matchups exist

For any aspect \(N\), count forward around the wheel:

- \(N\) **has an advantage against** \(N+1\) and \(N+2\).
- \(N\) **has a disadvantage against** \(N-1\) and \(N-2\).
- All other pairs are equal.

An advantage multiplies the score by 2. A disadvantage divides the score by 2.
Use the new score in the [resolution formula](../rules/index.md).

### The effect of the count

The number of aspects decides how many pairs are equal.

| Count | Advantage against | Disadvantage against | Equal to |
|---|---|---|---|
| 5 | 2 | 2 | 0 |
| 7 | 2 | 2 | 2 |

With five aspects, **no pair is equal**. Each combination of two aspects has a
result. A caster cannot select an aspect that is merely irrelevant.

With seven aspects, one third of the pairs are equal. A caster can select an
aspect that is neither good nor bad against the opposition.

### Proposed table for five aspects

The row acts on the column.

| Attacker | Hylogenesis | Anabiosis | Pyrolysis | Autophoresis | Anamnesis |
|---|---|---|---|---|---|
| **Hylogenesis** | — | ×2 | ×2 | ÷2 | ÷2 |
| **Anabiosis** | ÷2 | — | ×2 | ×2 | ÷2 |
| **Pyrolysis** | ÷2 | ÷2 | — | ×2 | ×2 |
| **Autophoresis** | ×2 | ÷2 | ÷2 | — | ×2 |
| **Anamnesis** | ×2 | ×2 | ÷2 | ÷2 | — |

### If matchups do not exist

Aspects then sort spells into groups, and nothing more. Each aspect has the
same effect against each target.

This is a smaller system, and it removes one decision from each cast. It also
removes the reason for a defence vector, because a defence vector with equal
values does nothing.

## Mixed aspects

A spell can use more than one aspect. Write the parts as a list of five values.
Each value is between 0 and 1. The total of the five values is 1.

Water is approximately \([0, 1, 0, 0, 0]\).

Each entity also has a list of five defence values. To find the effect against
a target, multiply each spell value by the matching defence value, then add the
five results.

A defence vector is only useful if the values differ. If
[matchups do not exist](#if-matchups-do-not-exist), this section has no
purpose.

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
