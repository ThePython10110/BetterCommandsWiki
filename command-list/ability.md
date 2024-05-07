# /ability

Gets and sets player privileges.

## Syntax

`ability <player: Selector> <ability: Privilege> [value: Boolean]`

`ability <player: Selector> [ability: Privilege]`

## Arguments

`player: Selector`

Specifies the player for which to grant/revoke/query the privilege.

`ability: Privilege`

Specifies the player privilege.

`value: Boolean`

Specifies the value to set the ability to, must be either `true` or `false`. If not specified, returns the current privilege's value.

## Result

Fails if the arguments are not specified correctly.

On success, sets the player privilege into the specified privilege. If `value: Boolean` isn't specified, returns whether the player has the specified privilege. If `ability: Privilege` isn't specified, returns what privileges the player has.

## History

| Version | Action           |
| ------- | ---------------- |
| v1.0    | Added `/ability` |
