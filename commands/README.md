---
description: The complete list of Better Commands
---

# Commands

| Command                                                                                      | Description                                                                                                      |
| -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `/? [<command>\|privs]`                                                                      | Alias for the built-in `/help` command                                                                           |
| [`/ability <player> <privilege> [<value>]`](ability.md)                                      | Gets and sets player privileges.                                                                                 |
| [`/bc <command>`](bc.md)                                                                     | Runs any Better Command (to deal with the problem of overriding commands)                                        |
| [`/clear [<targets>] [<item>] [<maxCount>]`](clear.md)                                       | Clears items from player inventory. Can also detect and query the amount of specified items.                     |
| [`/changesetting`](gamerule.md)                                                              | Alias for `/gamerule`                                                                                            |
| [`/clearspawnpoint [<targets>]`](clearspawnpoint.md)                                         | Clears respawn points set with /spawnpoint                                                                       |
| [`/damage <targets> <amount> [<damageType] [by <entity>]`](damage.md)                        | Applies a set amount of damage to the specified entities.                                                        |
| [`/enchant <targets> <enchantment> [<level>]`](enchant.md)                                   | Adds an enchantment to a player's selected item, subject to the same restrictions as an anvil (MCL only).        |
| [`/execute align\|as\|at\|facing\|positioned\|rotated\|run ...`](execute.md)                 | Runs a Better Command after changing the context)                                                                |
| [`/forceenchant <targets> <enchantment> [<level>]`](forceenchant.md)                         | Adds an enchantment to a player's selected item, regardless of whether it would normally be possible (MCL only). |
| [`/gamemode <gamemode> [<targets>]`](gamemode.md)                                            | Sets a player's gamemode                                                                                         |
| [`/gamerule <setting> [<value>]`](gamerule.md)                                               | Sets or queries a setting                                                                                        |
| [`/give <targets> <item>`](give.md)                                                          | Gives items to players                                                                                           |
| [`/giveme`](give.md)                                                                         | Alias for `/give @s`                                                                                             |
| [`/kill [<targets>]`](kill.md)                                                               | Kills entities (or self if `<targets>` left out)                                                                 |
| [`/killme`](kill.md)                                                                         | Alias for`/kill @s`                                                                                              |
| [`/me <action>`](me.md)                                                                      | Sends a message about yourself; can include target  selectors if you have the `server` privilege                 |
| [`/msg <targets> <message>`](msg.md)                                                         | Sends a private message; can include target selectors if you have the `server` privilege                         |
| [`/old <command>`](old.md)                                                                   | Runs any command overridden by a Better Command                                                                  |
| [`/playsound <sound> (<targets>\|<pos>) [<volume>] [<pitch>] [<maxDistance>]`](playsound.md) | Plays a sound                                                                                                    |
| [`/remove [<targets>]`](remove.md)                                                           | Removes entities (or self if `<entity>` left out)                                                                |
| [`/say <message>`](say.md)                                                                   | Sends a message to all connected players; can include target selectors if you have the `server` privilege        |
| [`/scoreboard objectives\|players ...`](scoreboard.md)                                       | Manipulates the scoreboard                                                                                       |
| [`/setblock <pos> <node> [keep\|replace]`](setblock.md)                                      | Places a node                                                                                                    |
| [`/setnode`](setblock.md)                                                                    | Alias for `/setblock`                                                                                            |
| [`/spawnpoint [<targets>]`](spawnpoint.md)                                                   | Sets players' respawn points                                                                                     |
| [`/summon <entity> [<pos>] [<rot>]`](summon.md)                                              | Summons an entity                                                                                                |
| [`/team add\|empty\|join\|leave\|list\|modify\|remove ...`](team.md)                         | Manipulates teams.                                                                                               |
| [`/teammsg <message>`](teammsg.md)                                                           | Sends a message to the executor's team                                                                           |
| [`/teleport ...`](teleport.md)                                                               | Sets entities' position and rotation (too many argument combinations).                                           |
| [`/tell`](msg.md)                                                                            | Alias for `/msg`                                                                                                 |
| [/tm](teammsg.md)                                                                            | Alias for `/teammsg`                                                                                             |
| [`/trigger <objective> [add\|set <value>]`](trigger.md)                                      | Allows players to set their own scores in controlled ways.                                                       |
| [`/tp`](teleport.md)                                                                         | Alias for `/teleport`                                                                                            |
| [`/w`](msg.md)                                                                               | Alias for `/msg`                                                                                                 |

## History

| Version | Action                                                                                                                                                                                                                                                                                                                                                                             |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| v1.0    | Added a whole bunch of commands that I don't want to list here                                                                                                                                                                                                                                                                                                                     |
| v2.0    | <p>Added <code>/gamemode</code>, <code>/enchant</code>, <code>/forceenchant</code>, <code>/teammsg</code>, <code>/spawnpoint</code>, <code>/clearspawnpoint</code>, <code>/clear</code>, <code>/gamerule</code>, <code>/changesetting</code>, <code>/remove</code>, and <code>/damage</code></p><p>Command outputs are now shown to other players and errors are shown in red.</p> |
