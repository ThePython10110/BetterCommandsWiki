---
description: The complete list of Better Commands
---

# Commands

| Command                                                                                | Description                                                                                               |
| -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `/? [<command>\|privs]`                                                                | Alias for the built-in `/help` command                                                                    |
| [`/ability <player> <priv> [true\|false]`](ability.md)                                 | Gets and sets player privs                                                                                |
| [`/bc <command>`](bc.md)                                                               | Runs any Better Command                                                                                   |
| [`/execute align\|anchored\|as\|at\|facing\|positioned\|rotated\|run ...`](execute.md) | Runs a Better Command after changing the context)                                                         |
| [`/gamemode <gamemode> [player]`](gamemode.md)                                         | Sets a player's gamemode                                                                                  |
| [`/give <player> <item> [count] [wear]`](give.md)                                      | Gives items to players                                                                                    |
| [`/giveme ...`](give.md)                                                               | Alias for `/give @s ...`                                                                                  |
| [`/kill [entity]`](kill.md)                                                            | Kills entities (or self if `<player>` left out)                                                           |
| [`/killme`](kill.md)                                                                   | Equivalent to `/kill @s`                                                                                  |
| [`/me <message>`](me.md)                                                               | Sends a message about yourself; can target  selectors if you have the `server` privilege                  |
| [`/msg <target> <message>`](msg.md)                                                    | Sends a private message; can include target selectors if you have the `server` privilege                  |
| [`/old <command>`](old.md)                                                             | Runs any command overridden by a Better Command                                                           |
| `/say <message>`                                                                       | Sends a message to all connected players; can include target selectors if you have the `server` privilege |
| `/summon <entity> [pos] [rot]`                                                         | Summons an entity                                                                                         |
| `/scoreboard objectives\|players ...`                                                  | Manipulates the scoreboard                                                                                |
| `/setblock <pos> <node> [keep\|replace]`                                               | Places a node (supports metadata/param1/param2)                                                           |
| `/setnode`                                                                             | Alias for `/setblock`                                                                                     |
| `/team add\|empty\|join\|leave\|list\|modify\|remove ...`                              | Manipulates teams.                                                                                        |
| `/teleport ...`                                                                        | Sets entities' position and rotation (too many argument combinations).                                    |
| [`/tell`](msg.md)                                                                      | Alias for `/msg`                                                                                          |
| `/trigger <objective> [add\|set <value>]`                                              | Allows players to set their own scores in controlled ways.                                                |
| `/tp`                                                                                  | Alias for `/teleport`                                                                                     |
| [`/w`](msg.md)                                                                         | Alias for `/msg`                                                                                          |
