---
description: 'Places a node (aliases: /setnode)'
---

# /setblock

## Syntax

`setblock <pos> <node> [keep|replace]`

## Arguments

`<pos>` [Position](../data-types.md#position)

Specifies the position of the block to be changed.

`<node>` [Node](../data-types.md#node)

Specifies the new node.

`[keep|replace]` [String](../data-types.md#string)

Specifies how to handle the node change. Must be one of:

* `keep` - Only air blocks are changed (non-air blocks are unchanged).
* `replace` - The node is set no matter what.

If not specified, defaults to `replace`.

Nodes are set with `minetest.set_node`, meaning that they do not activate the same callbacks as they would if placed by a player.

## History

| Version | Action                           |
| ------- | -------------------------------- |
| v1.0    | Added `/setblock` and `/setnode` |
