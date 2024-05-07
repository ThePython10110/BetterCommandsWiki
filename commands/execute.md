# /execute

Runs a Better Command after changing the context

## Usage

There are currently eight instructions (aka. subcommands) for the `/execute` command. Multiple subcommands can be chained after `/execute`. Subcommands are divided into 2 categories: Modifier subcommands and `run` subcommand.

* Modifier subcommands modify execution context variables to change the context the command is executed. Subcommands following it execute with specific executor(s), execution position(s), execution dimension(s), execution rotation(s) and execution anchor.
* `run` subcommand is used for carrying out another command.

All needed subcommands can be concatenated together. Subcommands other than the `run` subcommand can be arranged arbitrarily and used multiple times. But the `run` subcommand can be used only once and must be put at the end of the subcommands chain. A `run` subcommand or a condition subcommand finalizes the chain, otherwise the command is unparseable.

The game processes the subcommand chain in order from front to end, for example, the following commands are different:

All entities move one block forward: `execute as @e at @s run tp ^ ^ ^1` All entities are teleported to one block in front of the executor: `execute at @s as @e run tp ^ ^ ^1`

Some subcommands can fork the command execution into multiple branches, that is, they cause subcommands following it to be executed multiple times. For example, when `as` subcommand selects multiple entities, the subcommand following it executes once per entity.

If the `/execute` command hasn't ever forked, we describe it as having only one branch — the main branch.

A branch may terminate halfway and does nothing (does not execute `run` subcommands). For example, if the condition in a condition subcommand isn't met, or as subcommand selects zero entities. If all branches terminated, we describe the /execute command itself as terminating.

Note that `... run execute ...` has no effect at all. For example, the following commands work the same:

`execute as @e[type=pig] as @e[type=pig] run summon pig`

`execute as @e[type=pig] run execute as @e[type=pig] run execute run /execute run summon pig`

Better Commands' version of `/execute` acts like the non-coffee-flavored version of ACOVG in that it processes subcommands depth-first. This means that after forking, all the following subcommands are considered as a whole and are executed once for each branch.

There is no way to achieve breadth-first execution.

## Output values

I haven't quite figured this part out yet.

## Syntax

There are currently eight subcommands (eventually, there will be 12-13) for the `/execute` command, and each has its own special syntax, so describing syntax takes a large branching tree.

#### Full syntax tree

`/execute ...`

* `... align <axes> -> execute`
* `... anchored <anchor> -> execute`
* `... as <targets> -> execute`
* `... at <targets> -> execute`
* `... facing (<pos>|entity <targets> [anchor]) -> execute`
* `... positioned (<pos>|as <targets>) -> execute`
* `... rotated (<rot>|as <targets>) -> execute`
* `... run <command>`

where `-> execute` represents the start of another subcommand that is required.

#### Modifier subcommands

<details>

<summary><strong><code>align</code></strong></summary>

Updates the execution position, aligning to its current block position (integer coordinates). Applies only along specified axes. This akin to flooring the coordinates - i.e. rounding then \*downward\* (not toward zero).

_Usage_

`align <axes> -> execute`

_Arguments_

`<axes>`: String

Any non-repeating combination of the characters 'x', 'y', and 'z'. Axes can be declared in any order, but they cannot duplicate. (For example, `x`, `xz`, `zyx`, or `yz`.)

_Result_

Execution position in the given axes are floored, changing by less than 1 block. Causes an error if the argument is not specified correctly.

Given (-1.8, 2.3, 5.9), `execute align xz` changes the position to (-2, 2.3, 5).Given (2.4, -1.1, 3.8), `execute align yxz run tp @p ~ ~ ~` teleports the nearest player to (2, -2, 3).

</details>

{% hint style="warning" %}
The **`anchored`** subcommand currently does nothing. This will eventually change.
{% endhint %}

<details>

<summary><code>anchored</code></summary>

**anchored**

The `anchored` subcommand currently does nothing. This will change eventually.

Sets the _execution anchor_ to the eyes or feet. Defaults to feet.\
Running `positioned <pos> -> execute` resets to feet.

_Syntax_

`anchored <anchor> -> execute`

_Arguments_

`<anchor>`: `eyes` or `feet`

Whether to anchor the executed command to eyes or feet.

</details>

<details>

<summary><strong><code>as</code></strong></summary>

Sets the _executor_ to target entity, without changing _execution position, rotation, dimension, and anchor._

_Syntax_

`as <targets> -> execute`

_Arguments_

`<targets>`: Entity

Target entity/entities to become the new executor.

Must be a player name or [target selector](../target-selectors.md)

_Result_

Executor is updated to target entity (which changes the meaning of `@s`).

Causes an error if the argument is not specified correctly.

Forks if `<targets>` selects multiple entities.

Terminates current branch if `<targets>` fails to resolve to one or more entities (named players must be online).

_Example_

Kill all sheep: `execute as @e[type=sheep] run kill @s`

Teleport all loaded cows five blocks above you: `execute as @e[type=cow] run tp ~ ~5 ~`

</details>

<details>

<summary><strong><code>at</code></strong></summary>

Sets the _execution position, rotation,_ and _dimension_ to match those of an entity; does not change _executor_.

_Syntax_

`at <targets> -> execute`

_Arguments_

`<targets>`: Entity

Target entity/entities to match position, rotation, and dimension with. Must be a player name or [target selector.](../target-selectors.md)

_Result_

_Execution position, rotation,_ and _dimension_ are updated to match target entity.

Causes an error if the argument is not specified correctly.

Forks if `<targets>` selects multiple entities.

Terminates current branch if `<targets>` fails to resolve to one or more entities (named players must be online).

_Example_

Move all sheep upward 1 block: `execute as @e[type=sheep] at @s run tp ~ ~1 ~`

Kill the player running the command, because "`at`" does not change the executor: `execute at @e[type=sheep] run kill @s`\


</details>

{% hint style="warning" %}
Ignore any mention of the execution anchor. There is no `<anchor>` argument in the `facing` subcommand, although there will be eventually.
{% endhint %}

<details>

<summary><code>facing</code></summary>

Sets the _execution rotation_ to face a given point, as viewed from its anchor (either the eyes or the feet).

_**Syntax**_

`facing <pos> -> execute`

`facing entity <targets> <anchor> -> execute`

_**Arguments**_

Options: `facing <pos>`

`<pos>`: Position

Coordinates to rotate toward.

Must be three-dimensional coordinates. Accepts [tilde and caret notations](../coordinates.md).

Options: `facing entity <targets> <anchor>`

`<targets>`: Entity

The target(s) to rotate toward.

Must be a player name or [target selector](../target-selectors.md).

`<anchor>`: `eyes` or `feet`

Whether to face the target's _eyes_ or _feet_

Must be either `eyes` or `feet`.

_**Result**_

_Execution rotation_ is updated to face given position or targets.

Causes an error if the argument is not specified correctly.

Forks if `<targets>` selects multiple entities.

Terminates current branch if `<targets>` or `origin: target` fails to resolve to one or more entities (named players must be online).

_**Example**_

Executor rotates once to the left: `execute facing ^1 ^ ^ run tp @s ~ ~ ~ ~ ~`

All entities move one block in the direction of (0, 64, 0) (without changing their rotation): `execute as @e at @s facing 0 64 0 run tp @s ^ ^ ^1`

All entities move one block in the direction of (0, 64, 0) (with changing their rotation): `execute as @e at @s facing 0 64 0 run tp ^ ^ ^1 ~ ~`

All non player entities move one space in the direction of their nearest player (without changing their rotation): `execute as @e[type=!player] at @s facing entity @p feet run tp @s ^ ^ ^1`\


</details>

<details>

<summary><code>positioned</code></summary>

Sets the _execution position_, without changing _execution rotation_ or _dimension_; can match an entity's position

_**Syntax**_

`positioned <pos> -> execute`

`positioned as <targets> -> execute`

_**Arguments**_

Option: `positioned <pos>`

`<pos>`: Position

New position.

Must be three-dimensional coordinates. Accepts [tilde and caret notations](../coordinates.md).

Option: `positioned as <targets>`

`<targets>`:entity

The target(s) to rotate toward.

Must be a player name or [target selector](../target-selectors.md).

_**Result**_

_Execution position_ is updated. And `positioned <pos>` also resets _execution anchor_ to `feet`.

Causes an error if the argument is not specified correctly.

Forks if `<targets>` selects multiple entities.

Terminates current branch if `<targets>` or `origin: target` fails to resolve to one or more entities (named players must be online).

_**Example**_

Say the name of the player closest to (0, 64, 0): `execute positioned 0 64 0 run say @p`

</details>

