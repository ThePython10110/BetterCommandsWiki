---
description: Sets a player's game mode.
---

# /gamemode

## Syntax

`gamemode <gamemode> [<targets>]`

## Arguments

`<gamemode>` [String](../data-types.md#string)

Specifies the new game mode.

Must be one of the following:

* `survival` (can be abbreviated as `s` or `0`)
* `creative` (can be abbreviated as `c` or `1`)

`<target>` [Selector](../target-selectors.md)

Specifies the target(s). If not specified, defaults to the player who executes the command.

## Result

Changes the game mode of the player(s). In non-MineClone-like games, grants or revokes the `creative` privilege.

## History

| Version | Action            |
| ------- | ----------------- |
| v2.0    | Added `/gamemode` |
