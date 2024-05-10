---
description: Target selectors allow you to choose specific entities.
---

# Target Selectors

There are 6 selectors:

* A player name.
* `@s`: Self (the player or command block running the command)
* `@a`: All players
* `@e`: All entities
* `@r`: Random player
* `@p`: Nearest player

`@r` and `@p` can also select multiple players or other entities if using the `type` or `limit`/`c` **arguments** (explained below).

### Selector Arguments

Selectors support various arguments, which allow you to select more specific entities. To add arguments to a selector, put them in `[square brackets]` like this:

```
@e[type=mobs_mc:zombie,name=Bob]
```

You can include spaces if you want (although this many spaces seems a bit excessive):

```
@e [  type =  mobs_mc:zombie  ,  name = Bob ]
```

This selector selects all MCLA/VL zombies named Bob.

All arguments must be satisfied for an entity to be selected.

`@s` and player names do not support arguments.

Here is the current list of arguments:

<table data-card-size="large" data-view="cards" data-full-width="true"><thead><tr><th>Argument</th><th>Value type</th><th>Description</th><th>Example</th></tr></thead><tbody><tr><td><code>distance</code></td><td>Range</td><td>Distance from where the command was run</td><td><code>@e[distance=..10]</code> selects all entities within a 10-node radius (inclusive) of the execution position.</td></tr><tr><td><code>gamemode</code>/<code>m</code></td><td>String (<code>creative</code> or <code>survival</code>)</td><td>Filters entities based on gamemode (in non-MineClone-like games, they are filtered by whether they have the <code>creative</code> privilege). Non-players are excluded.</td><td><code>@a[gamemode=creative]</code> selects all players in creative mode.</td></tr><tr><td><code>level</code></td><td>Range</td><td>Filters entities based on their experience level (MineClone-like games only). Non-players are excluded.</td><td><code>@a[level=..5]</code> selects all players with 5 XP levels or less.</td></tr><tr><td><code>limit</code>/<code>c</code></td><td>Number</td><td>The maximum number of entites to match. <code>limit</code> and <code>c</code> do exactly the same thing, and only one can be included.</td><td><code>@e[sort=furthest, limit=5]</code> selects the furthest 5 entities.</td></tr><tr><td><code>lm</code>/<code>l</code></td><td>Number</td><td>Equivalent to <code>level=&#x3C;lm>..&#x3C;l></code> (<code>m</code> is for minimum)</td><td><code>@a[lm=5,l=23]</code> selects all players with 5 to 23 XP levels (inclusive).</td></tr><tr><td><code>name</code></td><td>String (can include spaces)</td><td>The name of the entity. Can use <code>!</code> to select only non-matching entities.</td><td><code>@a[name=!ThePython10110]</code> selects all players that do not have the name <code>ThePython10110</code>.</td></tr><tr><td><code>rm</code>/<code>r</code></td><td>Number</td><td>Equivalent to <code>distance=&#x3C;rm>..&#x3C;r></code> (<code>m</code> is for minimum)</td><td><code>@e[rm=4]</code> selects all entities outside of a 4-node radius (inclusive) of the execution position.</td></tr><tr><td><code>sort</code></td><td>String</td><td>The method for sorting entities. Can be Can be <code>arbitrary</code> (default for <code>@a</code> and <code>@e</code>), <code>nearest</code> (default for <code>@p</code>), <code>furthest</code>, or <code>random</code> (default for <code>@r</code>).</td><td><code>@e[sort=nearest,limit=1</code> selects the nearest entity.</td></tr><tr><td><code>type</code></td><td>String (entity ID or alias)</td><td>The type of entity (such as <code>mobs_mc:zombie</code>). Can use <code>!</code> to select only non-matching entities.</td><td><code>@e[type=player]</code> is equivalent to <code>@a</code> (but slower).</td></tr><tr><td><code>x</code>/<code>y</code>/<code>z</code></td><td>Absolute or relative coordinate</td><td>Changes the position for the <code>distance</code>/<code>rm</code>/<code>r</code> arguments. If one or more are left out, they stay the same.</td><td><code>@e[y=3.5, z=~-10, distance=..10]</code> selects all entities within a 10-node radius (inclusive) of <code>~ 3.5 ~-10</code> (relative to the execution position).</td></tr></tbody></table>



### Excluding with `!`

Some arguments (such as `name` and `type`) allow you to prefix the value with `!`. This means that it will match anything _except_ the entered value. For example, since `@e[type=player]` matches all players, `@e[type=!player]` matches all entities that are _not_ players. Arguments testing for equality cannot be duplicated, while arguments testing for inequality can. In other words, you can have as many `type=!<something>` as you want but only one `type=<something>`.

## History

| Version | Action                                                         |
| ------- | -------------------------------------------------------------- |
| v1.0    | Added target selectors                                         |
| v2.0    | Added `level`, `lm`/`l`, and `gamemode`/`m` selector arguments |
