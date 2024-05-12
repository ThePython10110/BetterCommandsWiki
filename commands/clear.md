---
description: >-
  Clears items from player inventory. Can also detect and query the amount of
  specified items.
---

# /clear

## Usage

Can remove items in the inventory lists specified by the "Clear Lists" setting. This defaults to `main,craft,offhand`.

## Syntax

`clear [targets] [item] [maxCount]`

## Arguments

`[targets]` Selector

Specifies the player(s) whose items are cleared. If not specified, defaults to the player who executes the command.

`[item]` Item

Specifies the item to be cleared. If not specified, or if `*`, all items are cleared.

If any metadata is included (including just `[]`, the item must match exactly; otherwise, only the names must match.

`[maxCount]` Number

Specifies the maximum number of items to be cleared. If not specified, or if `-1`, all items that match `[item]` are cleared. If `0`, instead of clearing items, detects and queries the amount of specified items.

## Examples

* To clear your entire inventory: `clear`
* To clear all items from Alice's inventory: `clear Alice`
* To clear all wool items from Alice's inventory: `clear Alice group:wool`
* To clear all orange wool items from the inventory of all players: `clear @a wool:orange`
* To clear all green wooden pickaxes from the nearest player
  * `clear @p default:pick_wood[color=green]`
* To test if a random player has stone in their inventory: `clear @r default:stone 0`

## History

| Version | Action         |
| ------- | -------------- |
| v2.0    | Added `/clear` |
