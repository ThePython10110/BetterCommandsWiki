---
description: Changes or queries the world's game time
---

# /time

## Syntax

`time add <time>`

Adds `<time>` to the in-game daytime.

`time query (daytime|gametime|day)`

Queries current time

`time set (day|night|noon|midnight|sunrise|sunset)`

`time set <time>`

Sets the internal daytime.

## Arguments

`<time>` String or Number

Specifies the time to add or set.

Must be a number with an optional unit suffix. Units include:

* `d`: an in-game day, 24000 ticks
* `s`: a second, 20 ticks
* `t` (default and omittable): a single tick, the default unit.

(Note: "ticks" don't really apply to Minetest, they're just defined here as 1/24000 of a day).

{% hint style="info" %}
In Minetest, 0 means midnight, and in ACOVG, 0 means dawn. If you want to change it, there's a setting (Use ACOVG time?) to do that.
{% endhint %}

`daytime|gametime|day` String

Specifies the time to query. Must be `daytime`, `gametime` or `day`.

* `daytime` - the number of game ticks since dawn. (the internal daytime modulo 24000)
* `gametime` - the age of the world in game ticks. (the game time modulo 2147483647)
* `day` - the number of in-game days passed. (the internal daytime divided by 24000, then modulo 2147483647)

`day|night|noon|midnight|sunrise|sunset` String

Specifies the time to set. Must be `day`, `night`, `noon`, `midnight`, `sunrise`, or `sunset`.

* `day` = 7000
* `night` = 19000
* `noon` = 12000
* `midnight` = 0
* `sunrise` = 5000
* `sunset` = 18000

{% hint style="info" %}
These commands do not affect the day count, unlike in ACOVG. Running `/time add 24000` is the same as `/time add 0`.
{% endhint %}

## Examples

* To set the time to 1,000: `time set 1000`

| Version | Action        |
| ------- | ------------- |
| v1.0    | Added `/time` |
