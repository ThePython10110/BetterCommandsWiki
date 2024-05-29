---
description: Applies a set amount of damage to the specified entities.
---

# /damage

## Usage

This command does not necessarily change an entity health value. Instead, it runs the code that is normally used to damage the entity.

The output text, result, and return value of the command are not related to whether the health value is changed.

The `<amount>` is not necessarily the final amount of reduced health value. The reduced health value can be less than or greater than the `<amount>` due to armor, status effects, and various other things.

## Syntax

`damge <target> <amount> [<damageType>] [by <entity>]`

## Arguments

`<target>` Selector

Specifies the entities to damage.

`<amount>` Number\
Specifies the amount of damage to inflict.

Must be a positive number. Value is floored to the nearest integer, since Minetest doesn't have floating-point damage (sadly).

`<damageType>` String

A valid Minetest damage type, such as `punch` or `fall` (defaults to `set_hp`). Only applies to players.

`<entity>` Selector

Specifies the entity who dealt the damage.

Should only select a single entity.

## Example

* Make a villager named `villager_1` deal 1 damage to the nearest iron golem:`/damage @e[type=iron_golem, sort=nearest, limit=1] 1 punch by @e[type=villager, limit=1, name="villager_1"]`

## History

| Version | Action          |
| ------- | --------------- |
| v2.0    | Added `/damage` |
