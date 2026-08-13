# Aspects

<p class="hatnote">For the operators that act on aspects, see <a href="../notation/">Spell Notation</a>.</p>

<div class="infobox" markdown>

### Aspects

|  |  |
|---|---|
| **Count** | 5 or 7 — undecided |
| **Named** | 5 |
| **Vector** | Dimension 5, sums to 1 |
| **Each carries** | An element, an operation, a domain |
| **Effect** | ±1 to \(\Delta\) |

</div>

Magic is divided into aspects. Each aspect has several **manifestations** — a
classical element, a basic database operation, and a domain — which are not
separate systems but the same thing seen from different angles.

The count is a root of \(x^2 - 12x + 35 = 0\). That is to say: five or seven,
undecided.

## The five

| # | Aspect | Element | Operation | Domain |
|---|---|---|---|---|
| 0 | **Hylogenesis** | Earth | Create | Matter |
| 1 | **Anabiosis** | Water | Update | Life |
| 2 | **Pyrolysis** | Fire | Delete | Energy |
| 3 | **Autophoresis** | Air | Move | *undecided* |
| 4 | **Anamnesis** | Aether | Read | Spells acting on spells |

Two placeholders, ⟨Aspect ζ⟩ and ⟨Aspect η⟩, wait on the five-or-seven
decision.

!!! note "Light is unassigned"
    Light is currently claimed by both Pyrolysis (as energy) and Anamnesis (as
    aether). It belongs to exactly one of them.

## The consequence nobody has priced in yet

**Aspects and verbs are now the same axis.**

This is the structural change, and it is larger than the renaming. Under the
previous model, [the five verbs](notation.md#verbs) were operators that applied
freely to any of seven types — five verbs × seven forms, thirty-five primitive
operations. Under this model each aspect *carries* an operation. Create is not
something you do to earth; Create **is** Hylogenesis.

So "unmake some earth" is no longer `∄ 🜃`. It is Pyrolysis acting on
Hylogenesis-matter — a two-aspect expression rather than a verb applied to a
form. The operator table and the aspect table are describing the same five
things twice.

That has to be resolved before either page is stable. Three readings:

1. **Aspects absorb the verbs.** The notation loses its separate verb column;
   a spell is a point in aspect space plus arguments. Cleanest, and it explains
   why five is the natural count — five classical elements including aether,
   five database operations.
2. **Verbs stay orthogonal**, and an aspect's "basic operation" is only the
   operation it performs *most naturally* — a flavour note, not a type rule.
   Preserves the thirty-five primitives.
3. **Both, at different layers.** Aspects are what magic is made of; verbs are
   what a caster writes. The compiler maps one to the other.

Tracked in [Open Questions](../design/open-questions.md#do-aspects-and-verbs-occupy-the-same-axis).

## Five or seven

The real trade-off is not tidiness of the number. It is **whether neutral
matchups exist at all.**

With any odd count \(n\), each aspect can beat \((n-1)/2\) others and lose to
the same number, giving a clean cycle with no ties. But the *shape* differs:

**Five aspects.** Each beats two, loses to two, and is neutral against nothing
but itself. Every matchup is decisive. This is the classic five-element wheel,
and it makes aspect choice maximally consequential — there is no safe pick and
no dead pairing.

**Seven aspects.** Each beats two, loses to two, and is *neutral against two*.
Roughly a third of all pairings are ties, which gives room for aspects that are
simply unrelated to each other, and lets a caster choose an aspect that is
merely irrelevant to the opposition rather than actively bad.

| | Beats | Loses | Neutral |
|---|---|---|---|
| **5 aspects** | 2 | 2 | 0 |
| **7 aspects** | 2 | 2 | 2 |

Five is the more aggressive design: it guarantees that every exchange has an
elemental story. Seven is the more forgiving one, and it needs two more
operations and two more elements to justify itself — which is a real cost,
since the five it has map onto the five database operations exactly.

### The cycle

For aspect \(N\) counting forward around the wheel, in either size:

- **Counters** \(N+1\) and \(N+2\)
- **Countered by** \(N-1\) and \(N-2\)
- **Neutral** with \(N\), and with \(N\pm3\) where those exist

### Matchup matrix, five aspects

Row acts on column. **+1** means the row aspect has advantage.

| Attacker \ Defender | Hylogenesis | Anabiosis | Pyrolysis | Autophoresis | Anamnesis |
|---|---|---|---|---|---|
| **Hylogenesis** | — | **+1** | **+1** | −1 | −1 |
| **Anabiosis** | −1 | — | **+1** | **+1** | −1 |
| **Pyrolysis** | −1 | −1 | — | **+1** | **+1** |
| **Autophoresis** | **+1** | −1 | −1 | — | **+1** |
| **Anamnesis** | **+1** | **+1** | −1 | −1 | — |

## Advantage is one doubling

Aspect advantage is worth **+1 to \(\Delta\)**, disadvantage **−1**.

A \(\Delta\) step is already a doubling, so an advantageous aspect does double
effect and a disadvantageous one half — the ×2 / ×0.5 multiplier the earlier
draft wanted, arriving from the scale rather than as a separate rule. The
matchup matrix and the resolution table speak the same units, and nothing extra
is multiplied at the table.

## Mixed aspects

A spell is a proportion of aspects: a vector of dimension five, all entries in
\([0,1]\), summing to 1. Water is approximately \([0,1,0,0,0]\).

An entity's aspect defences are likewise a vector. Effect against a target is
the dot product of the spell's aspect share with the target's defences.

<div class="stub" markdown>
Still unresolved: whether that dot product operates on multipliers (linear
space) or on \(\Delta\) offsets (log space). The two disagree for any spell
that is not purely one aspect, and the log-space reading is the one consistent
with the rest of the system.
</div>

## In-world theory

⟨Character III⟩ published four papers proving, in order:

1. There exists a function \(A(x)\), for \(x\) a mathematical object, returning
   the aspect vector required to create that object.
2. \(A(x)\) is well-defined for every mathematical object in ZFC.
3. \(\forall \epsilon > 0:\ \lim_{n \to \infty} P\left(1-\epsilon > \max A(x) > \tfrac{1}{5}+\epsilon \;\middle|\; K(x)=n\right) = 0\),
   where \(K\) is Kolmogorov complexity.
4. \(\forall x, y:\ A(x) = A(y) \implies K(x) = K(y)\)

The third is the interesting one in play. It says that as objects get more
complex, their aspect vectors stop being *mixed*: in the limit, a thing is
either near-perfectly balanced across all five aspects or almost purely one of
them, and the middle ground empties out. Complicated things are either
elemental or total.

The fourth is stronger than it looks — it makes the aspect vector a complete
invariant for complexity, so two objects sharing an aspect signature cannot
differ in how hard they are to specify.

Each paper ends with *"Ceterum censeo bears are fish."*

## Superseded

An earlier draft used seven aspects drawn from the three alchemical primes plus
the four classical elements — Body 🜔, Soul 🜍, Spirit ☿, Earth 🜃, Water 🜄,
Air 🜁, Fire 🜂. That set is replaced by the named aspects above. It is recorded
here because the seven-cycle matchup structure carried over intact, and because
the alchemical signs remain available as notation if the count settles at seven.
