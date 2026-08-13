# Combat

<p class="hatnote">For the curve every roll on this page uses, see <a href="../">Core Resolution</a>.</p>

Combat runs on a continuous timeline rather than rounds, weapons have a damage
profile across distance rather than a single range, and damage lands on body
parts rather than a pool of hit points.

<div class="stub" markdown>
This page is the least settled in the wiki. The structure below is agreed; the
numbers are not, and several sub-systems have competing versions recorded in
[Open Questions](../notes/open-questions.md).
</div>

## Initiative

Time is continuous and measured in seconds. There are no rounds and no turn
order — only a queue of scheduled events.

When combat begins, each combatant rolls `d100 / Agility`; that is how many
seconds pass before they first receive **priority**.

When you receive priority, you declare an action. Every action has three
phases, borrowed from fighting-game frame data:

| Phase | What it is |
|---|---|
| **Startup** | The commitment window. The action is declared and visible but has not happened. |
| **Active** | The action resolves — the attack lands, the spell takes effect. |
| **Endlag** | Recovery. You cannot act, and you are vulnerable. |

You receive priority again when your endlag expires. Because startup and endlag
are properties of the action rather than the character, a fast light attack and
a committed heavy one differ in *when you next get to decide*, not merely in
damage.

### Hitstun

Being hit adds **hitstun** — a delay pushing back the victim's next priority.

This is what makes spacing matter rather than merely flavouring it. Landing a
hit buys tempo, so a fast weapon that connects can keep an opponent from ever
reaching their own priority, and the fighting-game concept of frame advantage
appears without being imported as a special rule. It also gives the four
outcome tiers something to say beyond damage:

| Result | Effect on tempo |
|---|---|
| **CS** | Maximum hitstun; attacker acts again well before the defender |
| **NS** | Standard hitstun |
| **NF** | No hitstun; both proceed on schedule |
| **CF** | Attacker's own endlag extended — the whiff punish |

<div class="stub" markdown>
Open: whether hitstun scales with damage dealt, with the attacker's Power, or
is a flat property of the weapon. Flat is easiest to run; damage-scaled is
more realistic and risks unrecoverable lock-downs against low-Agility targets.
</div>

## Range bands

Weapons do not have *a* range. They have a **damage profile across range**, and
the profile is the point.

| Range | Distance | Characteristic weapons |
|---|---|---|
| **0** | Same square — grappling distance | Unarmed, dagger, knee, elbow |
| **1** | Arm's length | Sword, axe, mace |
| **2** | Reach | Spear, polearm, staff |
| **3+** | Missile | Bow, sling, thrown |

A spear does excellent damage at range 2 and *bad* damage at range 0, because a
man inside your point cannot be threatened by it. A dagger is the reverse. So
the fight becomes a contest over distance before it is a contest over damage —
which is what medieval combat actually looks like, and why footwork dominates
every historical treatise on it.

This interacts with initiative to produce the intended texture. Closing from
range 2 to range 0 costs an action, that action has startup, and the spearman
gets a free attempt during it. The dagger fighter must eat that risk to reach
the range where they win. Neither weapon is better; they want different
distances, and getting there is the game.

<div class="stub" markdown>
Needs writing: the actual damage-by-range table per weapon, whether the falloff
is a damage multiplier or a penalty to the score, and how reach works with the
square grid for diagonal distances.
</div>

## Stamina and wounds

Two separate systems, doing two different jobs.

### Stamina absorbs the attacks you avoid

Stamina is the pool spent on not being hit — dodging, parrying, shield work,
giving ground. Your own actions also drain it, so you get more vulnerable as
the fight goes on, and exhaustion is a mechanic rather than a description.

Resolving an incoming attack by the four tiers:

| Your dodge result | Outcome |
|---|---|
| **CS** | The attack does nothing at all |
| **NS** | The attack drains stamina |
| **NF** | The attack bypasses stamina and wounds you |
| **CF** | The attack crits |

If an attack exhausts your remaining stamina, the leftover carries through as a
wound. Stamina recovers far faster than wounds do.

### Wounds replace hit points

Each body part carries its own condition track. Damage to a location advances
that track, each step imposes worsening penalties, and past a threshold the
part is **disabled**.

This is not merely a flavour swap. Location-based damage means a wound impairs
the specific thing the part does — an arm stops holding a weapon, a leg stops
carrying Agility — so a fight degrades a character's capabilities rather than
draining an abstract number until they switch off at zero.

The scores plug straight in:

| Score | Role |
|---|---|
| **Toughness** | Length of each condition track — energy absorbed before tissue fails |
| **Stamina** | Size of the dodge pool |
| **Recovery** | Rate wounds clear |
| **Homeostasis** | Resistance to the poison and shock riders wounds carry |

!!! note "This fixes the objections to the earlier stamina model"
    The brainstorm raised two problems with attacks draining a merged
    health-stamina pool: what happens when you are paralysed and cannot dodge,
    and what happens when the arrow is poisoned. Splitting the systems answers
    both without a special case. A paralysed character simply has no stamina to
    spend, so every attack lands as a wound. A poisoned arrow deals its wound
    and the wound carries a status rider — which is a property of the wound,
    not of the pool it failed to drain.

<div class="stub" markdown>
On the realism question: a per-location condition track is considerably more
realistic than hit points, since real injury is local and impairing rather than
fungible. It is not *fully* realistic — actual trauma outcomes are dominated by
blood loss, shock and specific structure failure rather than a linear track,
and a bleed clock would model that better than another track step. Worth
deciding how far down that road to go before writing the tables, because a
bleed clock changes how long fights last more than any other single choice.
</div>

## Armour

Armour provides damage reduction; [Agility](ability-scores.md) avoids hits
altogether. The two defences are distinct and should not be merged.

- **Piercing** weapons can find gaps. On hitting a gap, the attack strikes the
  wearer directly rather than the armour.
- **Slashing** and **bludgeoning** cannot target gaps.
- **Bludgeoning** is effective *against* armour — it damages the armour itself
  and transmits through it.
- **Cleaving** lets an attack reach the wearer when it destroys the armour
  covering that location.

Armour is therefore consumable, and location-based, which lines it up exactly
with the wound system: armour covers locations, wounds land on locations, and
the same map serves both.

## Projectiles

A projectile is not an attack roll against a target. It is an object with a
position.

When fired, calculate the intended point of impact, the distance and the
projectile's speed. The projectile resolves after the corresponding travel
time, then traces every square between origin and destination and strikes the
**first creature** in its path.

Consequences worth keeping: you can shoot into a melee and hit your own side,
cover works because it is in the way rather than because it grants a bonus, and
a target who moves during the flight time is genuinely missed. It also means
the [initiative](#initiative) system and the projectile system are the same
event queue.
