---
description: 'Teleports entities (aliases: /tp)'
---

# /teleport

## Syntax

`teleport <destination>`

`teleport <targets> <destination>`

Teleports the executor or the specified entity(s) to the position of an entity, and make its rotation the same as the specified entity's.

`teleport <pos>`

Teleports the executor to a certain position.

`teleport <targets> <pos>`

Teleports the entity(s) to a certain position (without changing their rotation).

`teleport <targets> <pos> <rotation>`

`teleport <targets> <pos> facing <facingPos>`

`teleport <targets> <pos> facing entity <facingEntity>`

Teleports the entity(s) to a certain position and changes their rotation to the specified rotation.

## Arguments

`<targets>` [Selector](../data-types.md#selector)

Specifies the entity(s) to be teleported. If not specified, defaults to the command's executor.

`<pos>` [Position](../data-types.md#position)

Specifies the coordinates to teleport the target(s) to.

`<destination>` [Selector](../data-types.md#selector)

Specifies the entity to teleport the target(s) to.

`<rotation>` [Rotation](../data-types.md#rotation)

Specifies the rotation.

`<facingPos>` [Position](../data-types.md#position)

Specifies the coordinates to make the target(s) face towards.

`<facingEntity>` [Selector](../data-types.md#selector)

Specifies the entity to make the target(s) face towards.

## Examples

* To teleport the executing player to Alice: `teleport Alice`
* To teleport all players to the executing player: `tp @a @s`
* To teleport the executing player to x=100 and z=100, but three blocks above their current position: `teleport 100 ~3 100`
* To teleport the executing player 1 block forward `tp ^ ^ ^1`
* To rotate the nearest player 10 degrees to the right without changing their position: `execute as @p at @s run teleport @s ~ ~ ~ ~10 ~`

## History

| Version | Action                      |
| ------- | --------------------------- |
| v1.0    | Added `/teleport` and `/tp` |
