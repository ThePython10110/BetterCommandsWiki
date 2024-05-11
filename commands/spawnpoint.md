---
description: Sets players' respawn points
---

# /spawnpoint

## Syntax

`/spawnpoint [targets]`

## Arguments

`[targets]` [Selector](../data-types.md#selector)

The player(s) to set the spawnpoint for. If omitted, defaults to the executor.

Players' respawn points are set to the execution position. The only way to clear respawn points set with this command is the [`/clearspawnpoint`](clearspawnpoint.md) command.

## History

| Version | Action              |
| ------- | ------------------- |
| v2.0    | Added `/spawnpoint` |
