---
description: >-
  Adds an enchantment to a player's selected item, regardless of whether it
  would normally be possible (MCL only).
---

# /forceenchant

## Syntax

`forceenchant <targets> <enchantment> [<level>]`

## Arguments

`<targets>` Selector

Specifies the target(s).

`<enchantment>` String

Specifies the enchantment to be added to the item held in the target's main hand.

`<level>` Number

Specifies the enchantment level. If not specified, defaults to 1.

Must be a positive integer.

## Examples

*   To enchant the nearest player's held item with Depth Strider 200:

    `/forceenchant @a depth_strider 99` (try Soul Speed too... it's ridiculous)
*   To enchant the nearest player's held item with Knockback 99:

    `/forceenchant @p knockback 99` (just put it on a pair of boots or something... knockboots)

## History

| Version | Action                |
| ------- | --------------------- |
| v2.0    | Added `/forceenchant` |
