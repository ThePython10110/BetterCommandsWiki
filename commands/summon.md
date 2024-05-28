---
description: Summons an entity.
---

# /summon

## Syntax

`summon <entity> [<pos>] [<rot>]`

`summon <entity> [<pos>] [facing <target>]`

## Arguments

`<entity>` [String](../data-types.md#string) (entity ID or alias)

Specifies the entity to be summoned. You can include the entity's staticdata in \[square brackets]. If an entity alias is used, and the alias matches multiple different entities, chooses a random one.

`<pos>` [Position](../data-types.md#position)

Specifies the position to summon the entity. If not specified, defaults to the position of the command's execution.

`<rot>` [Rotation](../data-types.md#rotation)

Specifies the rotation (yaw and optionally pitch) of the summoned entity. If not specified, defaults to the rotation of the command's executor.

`<target>` [Selector](../target-selectors.md)

Specifies the entity the summoned entity should face.

## Examples

* To summon a zombie 10 blocks west of the current position of the executing player:
  * `summon mobs_mc:zombie ~-10 ~ ~`
* To summon a zombie 5 nodes in front of the executor, facing the executor:
  * `summon zombie ^ ^ ^5 facing @s`
* To summon a zombie 5 nodes behind the executor, facing north:
  * `summon zombie ^ ^ ^-5 0`

## History

<table data-full-width="false"><thead><tr><th>Version</th><th>Action</th></tr></thead><tbody><tr><td>v1.0</td><td>Added <code>/summon</code></td></tr></tbody></table>
