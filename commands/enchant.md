---
description: >-
  Adds an enchantment to a player's selected item, subject to the same
  restrictions as an anvil (MCL only).
---

# /enchant

## Usage

Can only be used to enchant items that can normally be enchanted (like tools and armor), and can only apply enchantments that can be obtained via normal enchanting. To override the game's normal enchantment restrictions, use [forceenchant.md](forceenchant.md "mention").

## Syntax

`enchant <targets> <enchantment> [<level>]`

## Arguments

`<targets>` Selector

Specifies the target(s).

`<enchantment>` String

Specifies the enchantment to be added to the item held in the target's main hand.

`<level>` Number

Specifies the enchantment level. Must not be greater than the maximum level for the specified enchantment. If not specified, defaults to 1.

Must be a positive integer.

## Examples

*   To give the Infinity enchantment to all players holding a bow:

    `/enchant @a infinity`
*   To enchant the nearest player's held sword with Sharpness 5:

    `/enchant @p sharpness 5`

## History

| Version | Action           |
| ------- | ---------------- |
| v2.0    | Added `/enchant` |
