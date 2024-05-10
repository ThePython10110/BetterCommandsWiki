---
description: Gets and sets player privileges.
---

# /ability

## Syntax

`ability <player> <ability> [value]`

`ability <player> [ability]`

## Arguments

`<player>` Selector

Specifies the player for which to grant/revoke/query the privilege.

Must be a player name or target selector.

`<ability>` or \[`ability]` String

Specifies the player privilege (such as `fly` or `server`).

`[value]` Boolean

Specifies the value to set the ability to, must be either `true` or `false`. If not specified, returns the current privilege's value.

## Result

Fails if the arguments are not specified correctly.

On success, sets the player privilege into the specified privilege. If `value: Boolean` isn't specified, returns whether the player has the specified privilege. If `ability: Privilege` isn't specified, returns what privileges the player has.

## History

| Version | Action           |
| ------- | ---------------- |
| v1.0    | Added `/ability` |
