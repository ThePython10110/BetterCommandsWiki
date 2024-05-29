---
description: >-
  Plays a specified sound to a player or in a location, and at a specific volume
  and pitch.
---

# /playsound

## Syntax

`playsound <sound> (<targets>|<pos>) [<volume>] [<pitch>] [<maxDistance>]`

## Arguments

`<sound>` String

Specifies the sound to play. Should be the filename of a sound (minus the extension), basically the same thing used for `minetest.sound_play`

`<targets>` Selector

Specifies the entities at whose position the sound will play.

`<pos>` Position

Specifies the position to play the sounds from.

`<volume>` Number

Specifies the value by which the volume will be multiplied. 1 is normal, 0.5 is half, 2 is double.

`<pitch>` Number

Specifies the value by which the pitch will be multiplied. 1 is normal, 0.5 is an octave down, 2 is an octave up.

`<maxDistance>` Number

The maximum distance from `<pos>` or `<targets>` at which the sound can still be heard.

## Examples

To play the sound of TNT igniting 3 nodes behind the nearest player:

`/execute as @p at @s run playsound tnt_ignite ^ ^ ^-3`

## History

| Version | Action             |
| ------- | ------------------ |
| v1.0    | Added `/playsound` |
