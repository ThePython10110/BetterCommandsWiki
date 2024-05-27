---
description: >-
  Adds an enchantment to a player's selected item, subject to the same
  restrictions as an anvil (MCL only).
---

# /enchant

## Syntax

`enchant <targets> <enchantment> [level]`

## Arguments

`<targets>` Selector

Specifies the target(s).

`<enchantment>` String

Specifies the enchantment to be added to the item held in the target's main hand.

`[level]` Number

Specifies the enchantment level. Should not be greater than the maximum level for the specified enchantment. If not specified, defaults to 1.

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
