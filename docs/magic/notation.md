# Spell Notation

<p class="hatnote">For the seven aspects these operators act on, see <a href="../aspects/">Aspects</a>.</p>

Magic is programming. A spell is an expression written in a formal notation,
and casting it is executing that expression. This page defines the operators.

## The model

An aspect is a **type** — what the spell acts on. An operator is a **verb** —
what it does. A spell that names only a type does nothing, in the same way that
`int` is not a program.

Spells are read left to right. Drawing order is evaluation order, which means
an observer watching a glyph take shape reads the head before the arguments: a
slow cast leaks its *shape* several beats before it leaks its *target*. You
know a triple-scatter unmaking is coming well before you know where it points.
Hidden information falls out of the notation itself rather than from a rule
about hidden information.

## Verbs

The five primitive operations on a typed cell — CRUD plus a pointer.

| Symbol | Name | Read as | Origin | Meaning | Example |
|---|---|---|---|---|---|
| ∃ | **Create** | make | Existential quantifier | Makes a new entity of the given aspect. Prefix. | `∃ 🜂@n4` — firebolt |
| ∄ | **Delete** | unmake | Negated existential | Removes the target. Requires ownership. Prefix. | `∄ 🜍Y` — reap the soul of Y |
| ? | **Read** | sense | The query sign | Loads a value without changing the target. Prefix. | `? ☿Y` — sense mana |
| → | **Update** | takes | Assignment | Writes a value. Target left, value right. | `🜂x → 0.9` |
| ↦ | **Convert** | becomes | Maps-to | Changes the aspect, not the value. | `x ↦ 🜄` — x becomes water |

## Handles and ownership

| Symbol | Name | Read as | Origin | Meaning | Example |
|---|---|---|---|---|---|
| ↓ | **Lock** | hold | Dijkstra's P | Takes a handle. The effect persists while held. Prefix. | `↓ (∃ 🜁@self)` |
| ↑ | **Release** | release | Dijkstra's V | Frees the handle. The effect ends. Prefix. | `↑ h` |
| ↪ | **Link** | links to | The hook arrow | The left entity becomes a reference to the right. | `a ↪ b` |
| ≅ | **Copy** | copy of | Congruence | Makes a second entity with the same structure. Prefix. | `≅ x` |
| ⊸ | **Move** | gives to | Linear implication | Transfers ownership; the source loses it. | `🜍self ⊸ g` |
| ⊢ | **Assert** | proves | Syntactic consequence | Proves a permission. Faults if the proof fails. Prefix. | `⊢ own(self, 🜍Y)` |

**Lock is concentration.** You hold a reference, the effect runs while you hold
it, and dropping concentration is `free(handle)` rather than a genre
convention.

### Death is access control

`∄ 🜍` — unmaking a soul — is Reaping. It is not blocked by *type* but by
*permission*: you may only free a pointer you own, and guardianship is the
ownership record.

The lich ritual is therefore three lines:

```
∃ t                    allocate an owner (the tefillah)
🜍self ⊸ t              transfer ownership of yourself to it
¬reaps(t)              disable that owner's automatic free
```

A chain of tefillin is a chain of owners, so revoking any one link simply
re-parents the lich upward.

!!! note "Make Soul does not exist"
    `∃ 🜍` is not forbidden — it is *unimplementable*. The guardianship tree has
    exactly one root and nobody holds write access to it. Daemons are therefore
    soulless by constraint rather than by choice, which closes the obvious hole
    ("why doesn't a binding-house just give theirs a soul?") with a reason no
    one can engineer around. It also means `∄ 🜍` aimed at a daemon is a null
    operation, so the zero in the Soul column of a daemon's defence vector
    arrives from the type system rather than from balance.

## Metaprogramming

| Symbol | Name | Read as | Origin | Meaning | Example |
|---|---|---|---|---|---|
| ∥ | **Fork** | and also | Parallel composition | Runs both sides at once. | `∃ 🜂@n1 ∥ ∃ 🜂@n2` |
| ⋈ | **Join** | joins | Relational join | Waits for both branches, then continues. | `h1 ⋈ h2` |
| ⌜ ⌝ | **Quote** | quote … unquote | Quine corners | Holds a spell as data without running it. Rank 7+. | `s → ⌜∄ 🜃@n3⌝` |
| ⌞ ⌟ | **Eval** | invoke | Inverted corners | Runs a quoted spell. | `⌞s⌟` |

## Modifiers

| Symbol | Name | Read as | Origin | Meaning | Example |
|---|---|---|---|---|---|
| ; | **Sequence** | then | Statement separator | Runs left, then right. | `↓h ; ∃ 🜂@n2` |
| ⇒ | **Trigger now** | if … do | If-then | Tests once; runs the right side if true. | `? ☿Y < 10 ⇒ ∄ 🜍Y` |
| ⇝ | **Trigger later** | when … do | Leads-to | Waits for the condition, using the event queue. | `@Y = @n3 ⇝ ∃ 🜂@n3` |
| △ | **Catch** | or else | CSP interrupt | Runs the right side if the left faults. | `∄ 🜍Y △ ∃ 🜂@Y` |
| ↯ | **Raise** | fault | Contradiction bolt | Causes a fault. Permission errors raise it. | `¬own(self,x) ⇒ ↯` |
| ↻ | **Repeat** | repeat | Cycle arrow | Repeats N times. Open stroke bounded; closed stroke unbounded, rank 5+. Prefix. | `↻3 (∃ 🜂@n4)` |
| ∀ | **Scatter** | for each | Universal quantifier | Runs the payload once per member of a set. Prefix. | `∀x ∈ S: ∄ 🜃x` |
| ⧗ | **Sleep** | wait | Hourglass | Delays the payload, using the event queue. Prefix. | `⧗1.5 (∃ 🜂@n4)` |
| @ | **At** | at | Address sign | Names a node or entity position. Prefix. | `@n4`, `@self` |
| ⊙ | **Within** | within | A centre and its region | The set of nodes within N edges. | `@self ⊙ 2` |

**Magnitude is not a modifier.** Damage, radius and duration are numeric
literals written as arguments. Making them operators bloats the vocabulary and
stops anything composing cleanly.

## Predicates

| Symbol | Name | Meaning |
|---|---|---|
| ¬ | Not | Inverts a test. Prefix. |
| ∧ | And | True if both are true. |
| ∨ | Or | True if either or both are true. |
| ⊻ | Xor | True if exactly one is true. |
| ∈ | Membership | True if the item is in the set. Use with ∀. |
| = | Equal | Tests two values. Nothing else uses `=`. |
| < ≤ > ≥ | Order | Compares numbers. Rank 3 spells need these. |

## Inversion

Verbs pair as inverses — Create/Delete, Read/Update, Lock/Release — so
inversion is a unary operator, and a mage who can write four verbs plus
inversion commands all of them.

The consequence worth keeping: **a misdrawn sign does not fizzle, it does the
opposite.** That is a far better failure mode for fiction than nothing
happening, and it makes a botched cast a scene rather than a lost turn.

## Rank

Rank is not a power level. It is *which operators you are permitted to write*,
which makes it checkable rather than asserted.

| Rank | Permitted |
|---|---|
| 0 | Verb + aspect + literal. Straight-line, no modifiers. |
| 1–2 | Repeat and Scatter with constant counts. Bounded, guaranteed to terminate. |
| 3–4 | Read feeding a predicate — the program branches on what it senses. |
| 5–6 | Computed or unbounded Repeat; self-reference. Termination undecidable from here up. |
| 7–8 | Quote — spells that emit spells. |
| 9 | Quote applied to Quote. The daemon spell lives here. |

**Rank 5 is where Rice's theorem bites**, and it is exactly where guild-certified
styluses stop. A safe wand is one that refuses to compile unbounded iteration —
which is, unavoidably, a wand that cannot express a daemon.

## Cost and time

- **Cast time is stroke count** — the length of the written expression.
- **Mana cost is operation count at runtime.**

These come apart, and that gap is the core tactical trade-off. `↻100` is three
strokes and a fortune in mana; the unrolled version is a hundred strokes and
cheap. It is a genuine time–space trade-off rather than a metaphor for one.

## Daemons

A daemon is a **closed ring that rewrites its own strokes** — self-modifying
code, which is simultaneously the mechanism of its apparent aliveness and the
reason a runaway spell cannot be halted: it has repaired its own gap.

### Daemons should be the optimal play

Binding and directing daemons is intended to be *better* than casting
everything by hand, and the mechanics should say so plainly. The setting's
anti-binding faction has materially grounded grievances and is still wrong on
the central question; a system where daemon use is a trap would contradict its
own fiction.

The design problem this creates is that a strictly dominant option stops being
a decision. The fix already exists in the lore: **no binder can prove a
daemon's obedience is more than a statistical tendency.** That converts
directly into the resolution system —

- A daemon acting on its own initiative resolves at **lower \(b\)** than the
  mage would. Same or better expected outcome, materially more variance.
- Direct casting is slower and costs the mage's own actions, but resolves at
  the mage's \(b\).

So daemons win on throughput and lose on predictability, which is the actual
shape of the real-world argument the setting is about. Handing critical,
narrow-tolerance work to a daemon is the mistake — not using one at all.

<div class="stub" markdown>
Open: the exact \(b\) penalty per daemon generation, and whether generations
5–6 close the gap entirely. See
[Open Questions](../design/open-questions.md#how-much-variance-do-daemons-carry).
</div>

## Geometry

The written form is **interlace** — parallel strands crossing over and under —
rather than a circle, which would read as direct homage to *Witch Hat Atelier*.

Braiding preserves everything structural. The loop-versus-arc distinction
survives as *topology* instead of geometry: an open braid has free ends and
terminates, a braid spliced into itself has no ends and runs forever. A
certified stylus is one that cannot draw a terminal splice.

| Element | Drawn as |
|---|---|
| **Aspect** | Strand treatment — solid, doubled, dashed, beaded, hatched, twist-corded, hollow. Texture, not colour, so it survives monochrome at thumbnail size. |
| **Create** | A free end blooming open |
| **Delete** | A cut or frayed terminus |
| **Read** | A tangent — strands touch and part without crossing |
| **Update** | A full crossing, strands trading position |
| **Lock** | A hitch, one strand wrapped around another and staying |
| **Inversion** | Which strand passes on top |
| **Cast time** | Literal length of the braid |

Three strands are three concurrent processes, so a spell that does two things
at once is *visibly wider*. Crossings that run with the aspect wheel lie flat;
crossings that run against it pull and fray, so an observer can spot a mage
doing something expensive without being told.
