---
description: Removes entities
---

# /remove

## Usage

Removes entities (like [`/kill`](kill.md), but doesn't call death callbacks). If the "Kill creative players" setting is disabled, players in creative mode (or with the `creative` privilege in non-MineClone games) cannot be killed.

## Syntax

`remove [<targets>]`

## Arguments

`<targets>` [Selector](../target-selectors.md)

Specifies the target(s) to remove. If not specified, defaults to the player who executed the command.

## Examples

* To kill the player executing the command: `kill @s` or `killme`
* To kill a player named ThePython: `kill ThePython`
* To remove all item entities: `kill @e[type=item]`
* To remove all entities except players: `kill @e[type=!player]`

## History

| Version | Action          |
| ------- | --------------- |
| v2.0    | Added `/remove` |
