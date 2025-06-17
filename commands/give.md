---
description: Gives items to one or more players
---

# /give

## Usage

Gives the specified item(s) to the target(s). If `<targets>` or `player: target` resolves to multiple targets, each receives the specified number of items.

This command gives all items in a single stack, exceeding normal stack limits if necessary. The maximum number of items that can be given is 65535.

## Syntax

`give <targets> <item>`

`giveme <item>` (equivalent to `/give @s <item>`)

## Arguments

`<targets>` [Selector](../target-selectors.md)

Specifies the target(s) to give item(s) to.

`<item>` [Item](../data-types.md#item-node)

Specifies the item to give.

## Examples

* To give the nearest player 50 blocks of dirt:
  * `/give @p default:dirt 50`
* To give all players a green half-worn wooden pickaxes:
  * `/give @a default:pick_wood[color=green] 1 32767`
* To give yourself 3 blue blocks of cobblestone:
  * `/giveme cobble[color=blue] 3`

## History

| Version | Action        |
| ------- | ------------- |
| v1.0    | Added `/give` |
