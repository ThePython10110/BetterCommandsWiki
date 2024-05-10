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

* `x`/`y`/`z`: Changes the position for the `distance`/`rm`/`r` arguments. If one or more are left out, they stay the same. For example, `@e[y=3.5, z=~-10, distance=..10]` selects all entities within 10 nodes of `~ 3.5 ~-10` (relative to where the command was run).
* `distance`: Distance from where the command was run. This supports ranges.
* `rm`/`r`: Identical to `distance=<rm>..<r>` (this is slightly different from ACOVG's usage, since it is inclusive and supports floats). `m` is for minimum.
* `name`: The name of the entity
* `type`: The entity ID (for example `mobs_mc:zombie`).
* `sort`: The method for sorting entities. Can be `arbitrary` (default for `@a` and `@e`), `nearest` (default for `@p`), `furthest`, or `random` (default for `@r`).
* `limit`/`c`: The maximum number of entites to match. `limit` and `c` do exactly the same thing, and only one can be included.
* `level`: Filters entities based on their experience level (MineClone-like games only). Non-players are excluded. This supports ranges.
* `lm`/`r`: Identical to `level=<lm>..<m>` (this is slightly different from ACOVG's usage, since it is inclusive and supports floats). `m` is for minimum.
* `gamemode`/`m`: Filters entities based on gamemode (in non-MineClone-like games, they are filtered by whether they have the `creative` privilege). Non-players are excluded. Valid values are currently `creative` and `survival`.



### Excluding with `!`

Some arguments (such as `name` and `type`) allow you to prefix the value with `!`. This means that it will match anything _except_ the entered value. For example, since `@e[type=player]` matches all players, `@e[type=!player]` matches all entities that are _not_ players. Arguments testing for equality cannot be duplicated, while arguments testing for inequality can. In other words, you can have as many `type=!<something>` as you want but only one `type=<something>`.

## History

| Version | Action                                                         |
| ------- | -------------------------------------------------------------- |
| v1.0    | Added target selectors                                         |
| v2.0    | Added `level`, `lm`/`l`, and `gamemode`/`m` selector arguments |
