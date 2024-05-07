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

**align**

Updates the execution position, aligning to its current block position (integer coordinates). Applies only along specified axes. This akin to flooring the coordinates - i.e. rounding then \*downward\* (not toward zero).

{% hint style="info" %}
what is a hint
{% endhint %}

