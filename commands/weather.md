---
description: Sets or queries the weather.
---

# /weather

## Syntax

`weather <weather> [<duration>]`

Sets the weather

`weather query`

Gets the weather

## Arguments

`<weather>` : String

The weather to set. Available options depend on the weather mod, but `rain` and `clear` work with all supported mods.

`[<duration>]` : String or number

The duration for the weather to last (MCL only).

Must be a number with an optional unit suffix. Units include:

* `d`: an in-game day, 24000 ticks
* `s`: a second, 20 ticks
* `t` (default and omittable): a single tick, the default unit.

(Note: "ticks" don't really apply to Minetest, they're just defined here as 1/24000 of a day).
