# Core Resolution

<p class="hatnote">For the scores that go into a check, see <a href="ability-scores/">Ability Scores</a>.</p>

This page gives the rule for all contested actions.

## The formula

The probability of success is:

\[ p = \frac{S^{b}}{S^{b} + D^{b}} \]

- \(S\) is the character's score.
- \(D\) is the difficulty, in the same units as \(S\).
- \(b\) is the skill factor.

Scores are quantities, not logarithms. A score of 2.0 is twice a score of 1.0.
A median adult human has a score of 1.0 in each ability.

Only the **ratio** \(R = S / D\) is important. If the character is three times
better than the task needs, \(R = 3\), and the result is the same at
\(S = 3, D = 1\) as at \(S = 300, D = 100\).

An opposed check needs no other rule. Make \(D\) the opponent's score.

## The skill factor

\(b\) sets how much the scores are important, against how much luck is
important.

| \(b\) | Effect |
|---|---|
| 0 | The scores do nothing. Each check is a coin toss. |
| 0.5 | Very unstable. |
| 1 | Luck is important, but the scores are also important. |
| 2 | Ability usually wins. |
| 4 | Almost no luck, unless the scores are close. |
| high | Luck does nothing. The result is known before the roll. |

Probability of success:

| \(R = S/D\) | b = 0.5 | b = 1 | b = 2 | b = 4 |
|---|---|---|---|---|
| 1 | 50% | 50% | 50% | 50% |
| 1.5 | 55% | 60% | 69% | 84% |
| 2 | 59% | 67% | 80% | 94% |
| 3 | 63% | 75% | 90% | 99% |
| 4 | 67% | 80% | 94% | 99.6% |
| 8 | 74% | 89% | 98% | 99.98% |

At \(b = 1\) the formula becomes \(p = S / (S + D)\). This is easy to do in
your head, and it is the recommended value if you do not want to calculate.

## The four results

There are four results: Critical Failure, Normal Failure, Normal Success and
Critical Success. Use the short forms **CF**, **NF**, **NS** and **CS**.

A result is critical if it does not change when the score changes by a factor
of three:

- You get a **CS** if you would also succeed with one third of your score.
- You get a **CF** if you would also fail with three times your score.

### Procedure

1. Calculate \(R = S / D\).
2. Calculate the three percentages: \(p(R/3)\), \(p(R)\) and \(p(3R)\).
3. Roll d100.
4. Read the result from the table.

| Result | Condition |
|---|---|
| **CS** | The roll is less than or equal to \(p(R/3)\). |
| **NS** | The roll is less than or equal to \(p(R)\). |
| **NF** | The roll is less than or equal to \(p(3R)\). |
| **CF** | The roll is more than \(p(3R)\). |

Read the table from the top. The first condition that agrees gives the result.

### Example

A character has \(S = 2.5\). The task has \(D = 1.0\). The skill factor is
\(b = 2\).

1. \(R = 2.5\)
2. \(p(R/3) = 41\%\), \(p(R) = 86\%\), \(p(3R) = 98\%\)
3. The roll is 62.
4. 62 is more than 41, but less than 86. The result is a **Normal Success**.

A roll of 41 or less gives a Critical Success. A roll of 99 or 100 gives a
Critical Failure.

### Critical rate

When the two sides are equal, the two critical results have the same
probability:

\[ P(\text{CS}) = P(\text{CF}) = \frac{1}{1 + 3^{b}} \]

| \(b\) | Critical rate, each side |
|---|---|
| 0.5 | 37% |
| 1 | 25% |
| 2 | 10% |
| 3 | 3.6% |
| 4 | 1.2% |
| 6 | 0.14% |

The skill factor thus controls two things at the same time: how unstable the
result is, and how frequently critical results occur.

## Where b comes from

\(b\) is not a free number. It comes from the quantity of noise in the
situation.

An action succeeds when the score, multiplied by luck, is more than the
difficulty. If luck multiplies the score by a random factor, and that factor
has a spread of \(s\) doublings, then:

\[ b = \frac{1}{s \ln 2} \]

Thus \(s\) is the quantity of luck, and \(b\) is its reciprocal. Measure the
noise, and the skill factor follows.

### Noise table

| Situation | \(s\) | \(b\) |
|---|---|---|
| No opponent. Known, unchanging conditions. | 0.10 | 14 |
| Trained work in a controlled place. | 0.25 | 6 |
| Casting a correct spell. | 0.40 | 3.5 |
| A contest against a person who thinks. | 0.75 | 2 |
| Disorder, or conditions that the rules do not model. | 1.5 | 1 |
| Almost pure chance. | 6 | 0.25 |

The maximum lift of a trained person changes by 3 to 5 percent from day to day.
This gives \(b \approx 20\). To lift a known weight is thus almost fully
reliable, and the table agrees.

### Why spells are reliable and fights are not

A spell is [a program](../magic/notation.md). A correct spell compiles and
runs. The act of casting adds very little noise.

A fight is the opposite. Your opponent tries to make your model of the
situation wrong. This is a definition of high noise. Training does not remove
it, because a different person makes the noise on purpose.

Thus low \(b\) belongs to **contests**, not to warriors. To lift a known weight
is as reliable as to cast a spell. A duel is not.

### The character part

Experts are more consistent, not only better. The two sources of noise combine:

\[ s^2 = s_{\text{task}}^2 + s_{\text{person}}^2 \]

At the table, move one line on the noise table:

- Move **down** (less reliable) if the character is hurt, tired, afraid, or has
  no training in the task.
- Move **up** (more reliable) if the character has expert training in that
  skill.

## Limits of the die

The d100 has 100 steps. When \(p\) is more than 99.5%, the die cannot change
the result. Do not roll. Tell the players what occurs.

This limit occurs sooner when \(b\) is large:

| \(b\) | The die stops being important when \(R\) is more than |
|---|---|
| 0.5 | 40000 |
| 1 | 200 |
| 2 | 14 |
| 4 | 4 |

At \(b = 4\), a character who is four times better than the task will always
succeed. This is correct behaviour. It shows you when to stop rolling.
