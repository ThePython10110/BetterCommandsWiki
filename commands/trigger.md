---
description: >-
  Changes the executor player's score in a scoreboard objective with a "trigger"
  criterion
---

# /trigger

Changes the executor player's score in a scoreboard objective with a "trigger" criterion, and un-enabled the objective for this player. Allows non-operator players to modify their own scoreboard objectives under tightly controlled conditions. Often used to let players activate systems controlled by data packs or command blocks.

## Syntax

`trigger <objective>`

Adds `1` to the current value of `<objective>`.

`trigger <objective> add <value>`

Adds `<value>` to the current value of `<objective>`.

`trigger <objective> set <value>`

Sets the value of `<objective>` to `<value>`.

## Arguments

`<objective>`: String

An enabled scoreboard objective with the "trigger" criterion.

It must be a single word containing only alphanumeric characters and underscores.

`<value>`: Number

Specifies the value to be set to or added to the objective.

Must be a 32-bit integer number (from -99,999,999,999,999 to 100,000,000,000,000).

## History

| Version | Action           |
| ------- | ---------------- |
| v1.0    | Added `/trigger` |
