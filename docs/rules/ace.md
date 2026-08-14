# Rule Language

Every rule in L.E.T.H.A.L. is written twice.

1. In **Attempto Controlled English (ACE 6.7)**. This version is the rule.
2. In ordinary English, with tables and examples. This version explains the
   rule.

If the two versions disagree, the ACE version is correct.

## Why

ACE is a subset of English. Each ACE sentence is correct English, but most
English sentences are not ACE. Each ACE sentence has exactly one meaning. A
parser assigns that meaning.

Ordinary rules text has ambiguity. A reader cannot always know if "and" joins
two conditions or two results, or if a phrase modifies the noun before it or
the verb. ACE removes this problem, because the grammar decides.

## How to read an ACE block

An ACE block looks like this:

```
If a check X has a roll N and X has a success-probability P and N =< P then X has a result that is a success.
```

Rules for a reader:

- Each sentence ends with a full stop.
- Each noun has a determiner: *a*, *the*, *every*, *no*, or a number.
- A capital letter, such as `X` or `N`, is a variable. It refers to the same
  thing in the rest of the sentence.
- A hyphen joins a compound word into one term: `skill-factor`,
  `critical-success`.
- The operator `=<` means "less than or equal to". The operator `>=` means
  "greater than or equal to".
- `If ... then ...` gives a conditional. The condition always comes first.

## How to write a new rule

1. Write the rule in ordinary English first.
2. Convert it to ACE. Use the constraints below.
3. Read the ACE sentence again. Find the meaning that the grammar gives.
4. If that meaning is not your meaning, write the sentence again.
5. Test the sentence in the [APE parser](http://attempto.ifi.uzh.ch/ape/).
6. Put the ACE version first on the page. Put the explanation after it.

### Constraints

| Rule | Correct | Not correct |
|---|---|---|
| Simple present tense only | `A player rolls a die.` | `A player rolled a die.` |
| Every noun has a determiner | `a card`, `every card` | `card` |
| Conditionals start with *If* | `If a card is valid then ...` | `A card is valid, so ...` |
| Relative clauses use who, which, that | `a card that is valid` | `a valid-looking card` |
| Passives name the agent | `A card is entered by a player.` | `A card is entered.` |
| Phrasal verbs are hyphenated | `A player looks-up a rule.` | `A player looks a rule up.` |
| No disjunction of nouns | `A player enters a card or enters a code.` | `A player enters a card or a code.` |

### Traps

These sentences are legal ACE, but they do not mean what a writer expects.

**A prepositional phrase modifies the verb, not the noun.**

`A player makes a check with a weapon.` says that the *making* uses the weapon.
For a check that has a weapon, write `a check that uses a weapon`.

**A relative clause modifies the noun immediately before it.**

`a copy of a rule that is wrong` says the *rule* is wrong. To say the copy is
wrong, use two sentences.

**The article *a* is existential, never general.**

`A mage casts a spell.` says that one mage casts one spell. For a general rule,
write `Every mage ...`.

**Quantifier scope follows word order.**

`A referee gives a difficulty to every check.` gives one difficulty to all
checks together. For one difficulty each, write
`For every check a referee gives a difficulty to the check.`

**Plural subjects are collective.**

`Two players lift a gate.` says the two players lift it together. For separate
lifts, write `Each of two players lifts a gate.`

<div class="stub" markdown>
The ACE blocks in this wiki are written to the ACE 6.7 specification. They are
**not yet verified by the APE parser**, because the machine that builds this
wiki cannot reach the parser. Test each block before you trust it. Correct any
block that the parser rejects, and record the correction.
</div>

## Scope

ACE states the **rules**. ACE does not state:

- Tables of numbers. A table is data, not a rule.
- Examples. An example demonstrates a rule.
- The design notes. Those pages hold arguments, and an argument needs ordinary
  English.
