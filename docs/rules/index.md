# Core Resolution

<p class="hatnote">For the scores that feed into a check, see <a href="ability-scores/">Ability Scores</a>. For unsettled questions arising from this page, see <a href="../design/open-questions/">Open Questions</a>.</p>

Every contested action in L.E.T.H.A.L. resolves through one curve. This page
defines it, the four outcome tiers, and the procedure for rolling it at a table.

## The curve

The chance of success is

\[ p = \frac{1}{1 + \left(\dfrac{\text{target number}}{\text{modifiers}}\right)^{b}} \]

Because [ability scores](ability-scores.md) are already base-2 logarithms, this
simplifies enormously. Write \(S\) for the character's relevant score and \(D\)
for the difficulty in the same units. Then modifiers \(= 2^{S}\), target number
\(= 2^{D}\), the ratio becomes a difference, and

\[ p = \frac{1}{1 + 2^{-b\Delta}}, \qquad \Delta = S - D \]

This is the logistic curve. **Nobody at the table multiplies or divides
anything** — you subtract difficulty from score and read one number off a table.

Opposed checks need no separate rule: set \(D\) to the opponent's score, and
\(\Delta\) is simply the gap between the two characters.

### What Δ means { #what-delta-means }

One point of \(\Delta\) is one doubling of the underlying physical quantity.
\(\Delta = +3\) means the character brings eight times what the task demands.
This is what makes the system scale without ceiling — a dragon and a dockworker
sit on the same axis, thousands of doublings apart, and the same table resolves
both.

## The skill factor

\(b\) controls how much the dice matter relative to the scores.

| \(b\) | Character of the roll |
|---|---|
| 0 | Scores are irrelevant. Every check is a coin flip. |
| 0.5 | Wildly swingy. Eight times overqualified still fails 20% of the time. |
| 1 | Noticeable luck, scores matter. |
| 2 | Competence usually tells. |
| 4 | Near-deterministic within a few doublings. |
| ∞ | Luck is irrelevant. Pass or fail is decided before the roll. |

Success probability by \(\Delta\) and \(b\):

| \(\Delta\) | b = 0.5 | b = 1 | b = 2 | b = 4 |
|---|---|---|---|---|
| **0** | 50% | 50% | 50% | 50% |
| **+1** | 58.6% | 66.7% | 80.0% | 94.1% |
| **+2** | 66.7% | 80.0% | 94.1% | 99.6% |
| **+4** | 80.0% | 94.1% | 99.6% | 99.998% |

Negative \(\Delta\) mirrors exactly: \(p(-\Delta) = 1 - p(\Delta)\).

!!! warning "Low b throws your ability scores away"
    This is the deciding consequence of the parameter. At \(b = 0.5\), a
    character eight times stronger than a task still fails one attempt in five.
    At \(b = 0.25\), a character a *thousand* times stronger fails 16% of the
    time. If you build infinitely scaling scores and then resolve them at low
    \(b\), the scores stop paying out. \(b\) is the throttle that decides
    whether the rest of the system means anything.

## The four tiers

Outcomes are Critical Failure, Normal Failure, Normal Success and Critical
Success — **CF**, **NF**, **NS**, **CS**.

The margin rule: a result is critical if it would still have gone that way
with modifiers three times worse (for a success) or three times better (for a
failure). A factor of three is a fixed offset on the \(\Delta\) axis:

\[ \log_2 3 \approx 1.585 \]

So the four tiers are a constant-width window sliding along the axis. Roll a
uniform \(r \in [0,1)\) and read down the list, first match winning:

| Outcome | Condition |
|---|---|
| **CS** | \(r < p(\Delta - 1.585)\) |
| **NS** | \(r < p(\Delta)\) |
| **NF** | \(r < p(\Delta + 1.585)\) |
| **CF** | otherwise |

!!! danger "Correction to the brainstorm notes"
    The notes list this cascade with the crit offsets swapped — CS tested
    against \(p(\Delta + 1.585)\) and NF against \(p(\Delta - 1.585)\). Because
    \(p\) increases with \(\Delta\), that ordering tests the *largest*
    threshold first and assigns **75% of all rolls at even odds to Critical
    Success**. The prose rule is right and the cascade transcribes it
    backwards: succeeding *despite* a 3× handicap means testing against
    \(\Delta - 1.585\), the harder curve. The table above is corrected.

### Crit rates

At even odds the tiers give a clean identity:

\[ P(\text{CS}) = P(\text{CF}) = \frac{1}{1 + 3^{b}} \]

| \(b\) | Crit rate each way at 50/50 |
|---|---|
| 0.5 | 36.6% |
| 1 | 25% |
| 2 | 10% |
| 3 | 3.6% |
| 4 | 1.2% |
| 6 | 0.14% |

This is the second reason \(b\) is the most consequential number in the system:
it sets swinginess and crit frequency together, from one dial.

## Rolling it at the table

The curve is continuous, so it needs a procedure. This one costs a single
lookup and one comparison.

Roll d100 and read its **swing** \(L\) from the table below. Then compute two
numbers from the check itself:

- **Edge** \(E = b\Delta\)
- **Crit window** \(W = 1.585b\)

Compare:

| Outcome | Condition |
|---|---|
| **CS** | \(L < E - W\) |
| **NS** | \(L < E\) |
| **NF** | \(L < E + W\) |
| **CF** | \(L \ge E + W\) |

\(b\) is a property of the task, not the roll, so \(E\) and \(W\) are computed
once per situation and reused for every check against it.

??? note "Why this works"
    Success requires \(r < p(\Delta) = 1/(1 + 2^{-b\Delta})\). Rearranging,
    that condition is exactly \(\log_2\!\big(r/(1-r)\big) < b\Delta\). The
    left side depends only on the die, so it can be tabulated once and
    reused for every value of \(b\) and \(\Delta\) forever. \(L\) is the
    roll's log-odds in base 2 — the same units as everything else in the
    system.

### The swing table

Read the tens down the left, the units across the top. \(L\) is negative on low
rolls, so **low is good**.

| d100 | +1 | +2 | +3 | +4 | +5 | +6 | +7 | +8 | +9 | +10 |
|---|---|---|---|---|---|---|---|---|---|---|
| **0** | -7.64 | -6.04 | -5.29 | -4.79 | -4.41 | -4.10 | -3.85 | -3.62 | -3.43 | -3.25 |
| **10** | -3.09 | -2.94 | -2.81 | -2.68 | -2.56 | -2.45 | -2.34 | -2.24 | -2.14 | -2.05 |
| **20** | -1.96 | -1.87 | -1.78 | -1.70 | -1.62 | -1.55 | -1.47 | -1.40 | -1.33 | -1.26 |
| **30** | -1.19 | -1.13 | -1.06 | -1.00 | -0.93 | -0.87 | -0.80 | -0.74 | -0.68 | -0.61 |
| **40** | -0.55 | -0.49 | -0.43 | -0.37 | -0.31 | -0.25 | -0.20 | -0.14 | -0.08 | -0.03 |
| **50** | +0.03 | +0.08 | +0.14 | +0.20 | +0.25 | +0.31 | +0.37 | +0.43 | +0.49 | +0.55 |
| **60** | +0.61 | +0.68 | +0.74 | +0.80 | +0.87 | +0.93 | +1.00 | +1.06 | +1.13 | +1.19 |
| **70** | +1.26 | +1.33 | +1.40 | +1.47 | +1.55 | +1.62 | +1.70 | +1.78 | +1.87 | +1.96 |
| **80** | +2.05 | +2.14 | +2.24 | +2.34 | +2.45 | +2.56 | +2.68 | +2.81 | +2.94 | +3.09 |
| **90** | +3.25 | +3.43 | +3.62 | +3.85 | +4.10 | +4.41 | +4.79 | +5.29 | +6.04 | +7.64 |

### Worked example

A character with Force 2.5 shoves a door whose difficulty is 1.0, at \(b = 2\).

- \(\Delta = 2.5 - 1.0 = 1.5\)
- \(E = 2 \times 1.5 = 3.0\), \(W = 1.585 \times 2 = 3.17\)
- Bands: CS below \(-0.17\), NS below \(3.0\), NF below \(6.17\), else CF.
- Roll 62 → \(L = +0.74\). That is under 3.0 but not under \(-0.17\): **Normal
  Success**.

Rolling 48 or less would have been a Critical Success; 99 or 100 a Critical
Failure.

## The die caps your range

d100 has finite resolution. The largest swing it can express is \(\pm 7.64\),
so once \(|E|\) exceeds that, the roll cannot change the outcome:

| \(b\) | Auto-resolves beyond |
|---|---|
| 0.5 | \(\|\Delta\| > 15.3\) |
| 1 | \(\|\Delta\| > 7.6\) |
| 2 | \(\|\Delta\| > 3.8\) |
| 4 | \(\|\Delta\| > 1.9\) |
| 6 | \(\|\Delta\| > 1.3\) |

This is a feature, not a defect — it is the system telling you when to stop
rolling. But note the interaction: **high \(b\) shrinks the band of \(\Delta\)
worth rolling for.** At \(b = 4\), any gap beyond two doublings is settled, and
you should narrate rather than roll. If you want dice to stay meaningful across
wide gaps, use a finer die (d1000 extends the range to \(\pm 11\)) or lower
\(b\).

## Open: how b gets assigned

The brainstorm sets \(b\) high for casting and low for martial activity, with
inconsistency as the price of playing a warrior. That rule is the one piece of
the system not derived from a modelled quantity, and it runs against the
physics: deadlifting a known weight off a firm floor is among the most
deterministic things a body does, while casting into unmodelled magical
conditions is not.

The alternative on the table is to make \(b\) **emergent** from two terms — how
completely the rules model the situation, plus a character term rising with
Composure, Attention and Will. Elite performers really are less variable, which
is a measured fact and therefore belongs in a simulationist system. Swinginess
survives as a penalty; it just stops being a class tax and becomes the mark of
a rattled or untrained operator.

This is unresolved. See [Open Questions](../design/open-questions.md#how-is-b-assigned).
