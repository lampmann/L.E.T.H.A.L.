# Aspects

<p class="hatnote">For the operators that act on aspects, see <a href="../notation/">Spell Notation</a>.</p>

<div class="infobox" markdown>

### The Seven Aspects

|  |  |
|---|---|
| **Count** | 7 |
| **Source** | Tria prima + classical elements |
| **Cycle** | Each beats 2, loses to 2 |
| **Neutral** | Self, +3, −3 |
| **Effect** | ±1 to \(\Delta\) |

</div>

Every spell is composed of the seven aspects, and every entity has aspect
defences. Aspects serve two purposes at once: they drive counter-based combat,
and they sort the spell list into categories.

## The seven

The set is the three alchemical primes followed by the four classical elements,
in their traditional order.

| # | Aspect | Sign | Domain |
|---|---|---|---|
| 0 | **Body** | <span class="sign">🜔</span> | Flesh, matter, durability |
| 1 | **Soul** | <span class="sign">🜍</span> | Life, death, guardianship |
| 2 | **Spirit** | <span class="sign">☿</span> | Mind, arcana, magic itself |
| 3 | **Earth** | <span class="sign">🜃</span> | Stone, weight, endurance |
| 4 | **Water** | <span class="sign">🜄</span> | Flow, ice, erosion |
| 5 | **Air** | <span class="sign">🜁</span> | Wind, lightning, movement |
| 6 | **Fire** | <span class="sign">🜂</span> | Heat, destruction |

The tria prima are Salt (Body), Sulphur (Soul) and Mercury (Spirit), which is
where the signs come from. Having three primes and four elements land in a
seven-cycle is a coincidence the system is entitled to exploit.

## The cycle

For any aspect \(N\), counting forward around the wheel:

- **Neutral** with \(N\), \(N+3\), \(N-3\)
- **Counters** \(N+1\) and \(N+2\)
- **Countered by** \(N-1\) and \(N-2\)

Every aspect therefore beats exactly two, loses to exactly two, and is neutral
against two plus itself. No aspect is universally strong, and none opts out.

### Matchup matrix

Row acts on column. **+1** means the row aspect has advantage.

| Attacker \ Defender | 🜔 Body | 🜍 Soul | ☿ Spirit | 🜃 Earth | 🜄 Water | 🜁 Air | 🜂 Fire |
|---|---|---|---|---|---|---|---|
| **🜔 Body** | — | **+1** | **+1** | 0 | 0 | −1 | −1 |
| **🜍 Soul** | −1 | — | **+1** | **+1** | 0 | 0 | −1 |
| **☿ Spirit** | −1 | −1 | — | **+1** | **+1** | 0 | 0 |
| **🜃 Earth** | 0 | −1 | −1 | — | **+1** | **+1** | 0 |
| **🜄 Water** | 0 | 0 | −1 | −1 | — | **+1** | **+1** |
| **🜁 Air** | **+1** | 0 | 0 | −1 | −1 | — | **+1** |
| **🜂 Fire** | **+1** | **+1** | 0 | 0 | −1 | −1 | — |

In prose: Body beats Soul and Spirit. Soul beats Spirit and Earth. Spirit beats
Earth and Water. Earth beats Water and Air. Water beats Air and Fire. Air beats
Fire and Body. Fire beats Body and Soul.

## Advantage is one doubling

Aspect advantage is worth **+1 to \(\Delta\)**, and disadvantage **−1**.

This is proposed rather than settled, but it is the reading that costs nothing.
A \(\Delta\) step is already defined as a doubling, so an advantageous aspect
does double damage and a disadvantageous one does half — the ×2 / ×0.5 matchup
multiplier the earlier draft wanted, arriving as a consequence of the scale
instead of a separate rule. The matchup matrix and the resolution table speak
the same units, and no additional multiplication appears at the table.

The alternative is a free-floating multiplier per matchup, which allows finer
tuning at the cost of a second numerical system nobody can hold in their head.

## Mixed aspects

A spell is a proportion of aspects, expressed as a length-7 vector — for
example a spell that is two-thirds fire and one-third air is
\([0,0,0,0,0,\tfrac13,\tfrac23]\).

An entity's aspect defences are likewise a length-7 vector; a creature immune
to fire and ordinary against everything else is \([1,1,1,1,1,1,0.1]\). Effect
against a given target is the dot product of the spell's aspect share with the
target's defence vector.

<div class="stub" markdown>
Unresolved: whether the dot product operates on multipliers (linear space) or
on \(\Delta\) offsets (log space). The two disagree for mixed-aspect spells,
and the log-space reading is the one consistent with the rest of the system.
Tracked in [Open Questions](../design/open-questions.md#aspects-in-linear-or-log-space).
</div>

## Rejected and open alternatives

**The 4+3 split.** An earlier proposal ran four elements plus three abstract
aspects, with one of them — Energy or Magic — fully neutral. It was set aside
on the grounds that a purely neutral aspect lets a caster opt out of the
matchup system entirely, which is the least interesting thing a player can do.

**Eight aspects.** Extending to eight makes the count a power of two and lets
one aspect stay neutral while the remaining seven keep a clean cycle. Still
live, and it trades the tidy tria-prima-plus-elements derivation for a tidier
number.

**Dual manifestation.** Each aspect having an elemental facet and a utility
facet — Water as both ice and life, Fire as both flame and destruction — is
already implicit in the domain column above. Whether that needs formalising
depends on how many non-elemental spells end up wanting a home.
