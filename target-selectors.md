# Target Selectors

Everywhere you would normally enter a player name, you can use a target selector instead. Target selectors let you choose multiple entities and narrow down exactly which ones you want to include.

There are 5 selectors:

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

`@s` ignores all arguments, unlike in ACOVG.

Here is the current list of arguments:

* `x`/`y`/`z`: Changes the position for the `distance`/`rm`/`r` arguments. If one or more are left out, they stay the same. For example, `@e[y=3.5, z=~-10, distance=..10]` selects all entities within 10 nodes of `~ 3.5 ~-10` (relative to where the command was run).
* `distance`: Distance from where the command was run. This supports ranges.
* `rm`/`r`: Identical to `distance=<rm>..<r>` (this is slightly different from ACOVG's usage, since it is inclusive and supports floats). `m` is for minimum.
* `name`: The name of the entity
* `type`: The entity ID (for example `mobs_mc:zombie`).
* `sort`: The method for sorting entities. Can be `arbitrary` (default for `@a` and `@e`), `nearest` (default for `@p`), `furthest`, or `random` (default for `@r`).
* `limit`/`c`: The maximum number of entites to match. `limit` and `c` do exactly the same thing, and only one can be included.
