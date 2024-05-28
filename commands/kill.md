---
description: Kills entities (players, mobs, items, etc.).
---

# /kill

## Usage

Kills entities. If, for some reason, entities do not die when attempting to kill them, please report it on the [GitHub issue tracker](https://github.com/ThePython10110/better\_command\_blocks/issues) (make sure to include the mod and entity name). If the "Kill creative players" setting is disabled, players in creative mode (or with the `creative` privilege in non-MineClone games) cannot be killed.

## Syntax

`kill [<targets>]`

`killme` (equivalent to `kill @s`)

## Arguments

`<targets>` [Selector](../target-selectors.md)

Specifies the target(s) to kill. If not specified, defaults to the player who executed the command.

## Examples

* To kill the player executing the command: `kill @s` or `killme`
* To kill a player named ThePython: `kill ThePython`
* To kill all item entities: `kill @e[type=item]`
* To kill all entities except players: `kill @e[type=!player]`

## History

| Version | Action                                                                                 |
| ------- | -------------------------------------------------------------------------------------- |
| v1.0    | Added `/kill`                                                                          |
| v1.1    | Removed debug logging when using `/kill`                                               |
| v2.0    | Fixed a bug keeping the `/kill` command from killing players in certain circumstances. |
