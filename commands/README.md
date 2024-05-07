# Commands

| Command                                                                                | Description                                                                                          |
| -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `/? [<command>\|privs]`                                                                | Alias for the built-in `/help` command                                                               |
| [`/ability <player> <priv> [true\|false]`](ability.md)                                 | Gets and sets player privs                                                                           |
| [`/bc <command>`](bc.md)                                                               | Runs any Better Command                                                                              |
| [`/execute align\|anchored\|as\|at\|facing\|positioned\|rotated\|run ...`](execute.md) | Runs a Better Command after changing the context)                                                    |
| `/gamemode <gamemode> [player]`                                                        | Sets a player's gamemode                                                                             |
| `/give <player> <item> [count] [wear]`                                                 | Gives items to players (or self if `<player>` left out)                                              |
| `/giveme ...`                                                                          | Alias for `/give @s ...`                                                                             |
| `/kill [entity]`                                                                       | Kills entities (or self if `<player>` left out)                                                      |
| `/killme`                                                                              | Equivalent to `/kill @s`                                                                             |
| `/me <message>`                                                                        | Sends a message about yourself; can include entity selectors if you have the `server` priv           |
| `/msg`                                                                                 | Alias for `/tell`                                                                                    |
| `/old <command>`                                                                       | Runs any command overridden by a Better Command                                                      |
| `/say <message>`                                                                       | Sends a message to all connected players; can include entity selectors if you have the `server` priv |
| `/summon <entity> [pos] [rot]`                                                         | Summons an entity                                                                                    |
| `/scoreboard objectives\|players ...`                                                  | Manipulates the scoreboard                                                                           |
| `/setblock <pos> <node> [keep\|replace]`                                               | Places a node (supports metadata/param1/param2)                                                      |
| `/setnode`                                                                             | Alias for `/setblock`                                                                                |
| `/team add\|empty\|join\|leave\|list\|modify\|remove ...`                              | Manipulates teams.                                                                                   |
| `/teleport ...`                                                                        | Sets entities' position and rotation (too many argument combinations).                               |
| `/tell <player> <message>`                                                             | Sends a private message; can include entity selectors if you have the `server` priv                  |
| `/trigger <objective> [add\|set <value>]`                                              | Allows players to set their own scores in controlled ways.                                           |
| `/tp`                                                                                  | Alias for `/teleport`                                                                                |
| `/w`                                                                                   | Alias for \[`/tell`]                                                                                 |
