---
description: Controls teams.
---

# /team

## Syntax

`team list [<team>]`

Lists all teams, with their display names and the amount of entities in them. The optional `[team]` can be used to specify a particular team.

`team add <team> [<displayName>]`

Creates a team with the given name and optional display name. `[displayName]` defaults to `<team>` when unspecified.

`team remove <team>`

Deletes the specified team.

`team empty <team>`

Removes all members from the named team.

`team join <team> [<members>]`

Assigns the specified entities to the specified team. If no entities are specified, makes the executor join the team.

`team leave [<members>]`

Makes the specified entities leave their teams. If no entities are specified, makes the executor leave their team.

`team modify <team> <option> <value>`

Modifies the options of the specified team.

## Arguments

`<team>` [String](../data-types.md#string)

Specifies the name of a team.

Must be a single word containing only alphanumeric characters and underscores.

`<displayName>` [Long string](../data-types.md#long-string)

Specifies the team name to be displayed.

`<members>` [Selector](../target-selectors.md) or (../data-types.md#string)

Specifies the entities to join or leave the team.

It must be either a target selector, a fake player name, or `*` for all score holders being tracked by the scoreboard system. Named players do not have to be online.

`<option>`

A specific option to change.mo

Value must be one of the following:

* `displayName`: Set the display name of the team.
* `color`: Decide the color of the team and players in chat and on the sidebar.
* `friendlyFire`: Enable/Disable players inflicting damage on each other when on the same team. In non-MineClone games, only affects direct damage (so players can still use arrows or other things).
* `nameFormat`: Set how player names appear in chat and the sidebar.

`<value>`

Specifies the value to set `<option>` to.

Shown below are the values for each option.

* For `displayName`:
  * `<displayName>`: [Long string](../data-types.md#long-string) - specifies the team name to be displayed.
* For `color`:
  * `<color>`: [String](../data-types.md#string) - Must be a valid team color.
* For `friendlyFire`:
  * `<allowed>`: [Boolean](../data-types.md#boolean)
    * `true` - (Default) Enables players inflicting damage on each other when in the same team.
    * `false` - Disable players inflicting damage on each other when in the same team.
* For `nameFormat`:
  * `<nameFormat>`: [Long string](../data-types.md#long-string) - Any string, where any instance of `%s` is replaced with the player's name.
    * A player named ThePython on a team with the format `[ADMIN] %s the Great` would appear as `[ADMIN] ThePython the Great`.

## History

| Version | Action         |
| ------- | -------------- |
| v1.0    | Added `/team`1 |
