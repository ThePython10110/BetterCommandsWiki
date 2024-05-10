---
description: Gets and sets player privileges.
---

# /ability

## Syntax

`ability <player> [ability] [value]`

## Arguments

`<player>` [Selector](../data-types.md#selector)

Specifies the player for which to grant/revoke/query the privilege.

Must be a player name or target selector.

`[ability]` [String](../data-types.md#string)

Specifies the player privilege (such as `fly` or `server`).

`[value]` [Boolean](../data-types.md#boolean)

Specifies the value to set the ability to, must be either `true` or `false`. If not specified, returns the current privilege's value.

## Result

Fails if the arguments are not specified correctly.

On success, sets the player privilege into the specified privilege. If `[value]` isn't specified, returns whether the player has the specified privilege. If `<ability>` isn't specified, returns what privileges the player has.

## History

| Version | Action           |
| ------- | ---------------- |
| v1.0    | Added `/ability` |
