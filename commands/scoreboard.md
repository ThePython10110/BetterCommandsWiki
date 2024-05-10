---
description: Manages and displays scores for various scoreboard objectives.
---

# /scoreboard

## Objectives subcommands

### Syntax

`scoreboard objectives list`

Lists all existing objectives with their display names and criteria

`scoreboard objectives add <objective> <criterion> [displayName]`

Creates a new objective with the givven internal objective name, specified criterion, and the optional display name.

`scoreboard objectives remove <objective>`

Deletes the named objective from the scoreboard system. Data is deleted from the objectives list, and if it was on a display list it is no longer displayed.

`scoreboard objectives setdisplay <slot> [objective] [ascending|descending]`

Displays score info for the objective in the given slot. Note that the objective parameter is optional; if no objective is provided, this display slot is cleared (returned to its default state). If slot is `sidebar`, there is an additional optional argument `ascending|descending` to specify the sort order (added in v2.0).

`scoreboard objectives modify <objective> displayname <displayName>`

Changes the display name of the scoreboard in display slots.

`scoreboard objectives modify <objective> numberformat`

Resets the default number format of the scoreboard in display slots.

`scoreboard objectives modify <objective> numberformat blank`

Sets the default number format to blank, which indicates that the score is not shown.

`scoreboard objectives modify <objective> numberformat fixed <contents>`

Sets the default number format to fixed, which indicates that the score is replaced by `<contents>`.

`scoreboard objectives modify <objective> numberformat styled <color>`

Sets the default number format to styled, which indicates that the score is displayed with the selected color.

### Arguments

`<objective>` String

Specifies the internal objective name.

Must be a single word, containing only alphanumeric characters and underscores.

`<criterion>` String

Specifies the criterion of the new objective. Must be a valid scoreboard objective criterion.

`<displayName>` Long string

Specifies the display name, defaulting to `<objective>` when unspecified

`<slot>` String

Specifies the slot to display the objective. Must be a scoreboard display slot. Valid slots are `sidebar` and `sidebar.<color>` where `<color>` is a valid team color.

`[ascending|descending]`

Specifies the sort order.

`<contents>` Long text

Specifies the text to show instead of a score.

`<color>` String

Any valid [Minetest colorstring](https://api.minetest.net/colors) or team color.

## Players commands

### Syntax

`scoreboard players list [targets]`

Lists all score holders that are tracked in some way by the scoreboard system. The optional `[targets]` parameter is used to list the scores of particular score holders.

`scoreboard players get <target> <objective>`

Returns the scoreboard value.

`scoreboard players set <targets> <objective> <score>`

Set the targets' scores in the given objective, overwriting any previous score.

`scoreboard players add <targets> <objective> <score>`

Increments the targets' scores in that objective by the given amount. A negative number subtracts from the score.

`scoreboard players remove <targets> <objective> <score>`

Decrements the targets' scores in that objective by the given amount. A negative number adds to the score.

`scoreboard players reset <targets> [objective]`

Deletes score or all scores for the targets. If `[objective]` is specified, then only that objective is cleared. Otherwise, this applies to all objectives.

Note that this does not merely set the scores to 0: it removes the targets from the scoreboard system (or for the given objective) altogether.

This also disables the target players' ability to use `/trigger` command (on the given objective if specified).

`scoreboard players test <player> <objective> [min] [max]`

Test if scores are between min and max (`[min]` and `[max]` default to -99,999,999,999,999 and 100,000,000,000,000 if not specified or `*`).

`scoreboard players enable <targets> <objective>`

Enables the target(s) to use the `/trigger` command on the specified objective. This command accepts non-player entities, but only players are able to actually use the `/trigger` command. Until this command has been run, players can't trigger that objective.

Using the `/trigger` command disables it again.

Note that if any of the targets did not previously have a score for that scoreboard, this command sets their score to 0.

`scoreboard players operation <targets> <targetObjective> <operation> <source> <sourceObjective>`

Applies an arithmetic operation altering the targets' scores in the target objective, using sources' scores in the source objective as input.

`scoreboard players display name <targets> <objective> [displayName]`

Changes the display name of the targets' scores (if `[displayName]` is not specified, display name is reset).

`scoreboard players display numberformat <targets> <objective> blank`

Sets the number format of the targets' scores to blank, which indicates that the score is not shown.

`scoreboard players display numberformat <targets> <objective> fixed <contents>`&#x20;

Sets the number format of the targets' scores to fixed, which indicates that the score is replaced by `<contents>`.

`scoreboard players display numberformat <targets> <objective> styled <color>`

&#x20;Sets the number format of the targets' scores to styled, which indicates that the score is displayed with the selected color.

### Arguments

`<target>` Selector or String

Specifies the score holder.

It must be either a target selector, a fake player name, or `*` for all score holders being tracked by the scoreboard system. Named players do not have to be online.

`<targets>` Selector or String

Specifies the score holders.

It must be either a target selector, a fake player name, or `*` for all score holders being tracked by the scoreboard system. Named players do not have to be online.

`<objective>` String

Specifies the internal objective name

Must be a single word containing only alphanumeric characters and underscores.

`<score>` Number

Specifies the new score, or an amount to add/subtract from the score. Must be a number from -99,999,999,999,999 to 100,000,000,000,000.

`[min]`/`[max]` Number or `*`

Specifies the minimum and maximum value.

Must be a number from -99,999,999,999,999 to 100,000,000,000,000.

If not specified, or `*`, default is minimum or maximum value, respectively.

`<targetObjective>` String

Specifies the objective for targets.&#x20;

Must be a single word containing only alphanumeric characters and underscores.

`<source>` Selector or String

Specifies the source score holders whose scores are used as source inputs.

It must be either a target selector, a fake player name, or `*` for all score holders being tracked by the scoreboard system. Named players do not have to be online.

`<operation>` String

Specifies the operation to be applied.

Valid values:

* `=` Assignment: Set target's score to source's score
* `+=` Addition: Add source's score to target's score
* `-=` Subtraction: Subtract source's score from target's score
* `*=` Multiplication: Set target's score to the product of the target's and source's scores
* `/=` Floor division: Divide target's score by source' scores, and the result is rounded down to an integer.
* `%=` Modulus: Divide target's score by source's score, and use the positive remainder to set the target score
* `><` Swapping: swaps target's score and source's score
* `<` Choosing minimum: Set target's score to source's score only if source's score is less.
* `>` Choosing maximum: Set target's score to source's score only if source's score is bigger.

In all cases except `><`, source's score remains unchanged when performing the operation on a target. If target or source isn't tracked by the specified objective, it is set to 0. If more than one score holder is specified as sources, performs the operation once with each source's score. If more than one target score holder is specified, performs the operation for each target one by one.

`[displayName]` Long string

Specifies the display name.

`<contents>` Long string

Specifies display text

`<color>` String

Any valid [Minetest colorstring](https://api.minetest.net/colors) or team color.

## History

<table><thead><tr><th width="341">Version</th><th>Action</th></tr></thead><tbody><tr><td>v1.0</td><td>Added <code>/scoreboard</code></td></tr><tr><td>v2.0</td><td>Added <code>picked_up.&#x3C;itemstring></code>, <code>mined.&#x3C;itemstring></code>, <code>dug.&#x3C;itemstring></code>, <code>placed.&#x3C;itemstring></code>, and <code>crafted.&#x3C;itemstring></code> scoreboard criteria</td></tr></tbody></table>
