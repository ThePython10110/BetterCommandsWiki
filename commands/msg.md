---
description: 'Sends a private message to one or more players. (aliases: /w, /tell)'
---

# /msg

## Syntax

`msg <targets> <message>`

## Arguments

`<targets>` [Selector](../target-selectors.md)

Specifies the player(s) to send the message to.

`<message>` [Long string](../data-types.md#long-string)

Specifies the message to tell.

Can include target selectors if executed by a command block or a player with the `server` privilege.

## Examples

* To privately tell ThePython10110 to start the game: `tell ThePython10110 Start the game!`
* To say "Hi" to all online players: `msg @a Hi`
* To whisper to TestMiner instructions to trap MineTester: `w TestMiner Trap MineTester now!`

## History

| Version | Action                          |
| ------- | ------------------------------- |
| v1.0    | Added `/msg`, `/tell`, and `/w` |
