---
description: Allows entities to mount or dismount other entities.
---

# /ride

## Usage

Attaches entities to each other using Luanti's built-in attachment system. Does not have any way of automatically putting entities in the right place.

## Syntax

`ride <target> mount <vehicle> [<bone>] [<pos>] [<rot>]`

`ride <target> start_riding <vehicle> [<bone>] [<pos>] [<rot>]`

Attaches `<target>` to `<vehicle>` at the given bone, with the given position and rotation.

`ride <target> dismount`&#x20;

`ride <target> stop_riding`

Dismounts `<target>` from any vehicle it is riding.

## Arguments

`<target>`: Target selector

Specifies the passenger.

Must be a player name or target selector. Should only select one entity.

`<vehicle>`: Target selector

Specifies the mount.

Must be a player name or target selector. Should only select one entity.

`[<bone>]`: String

The bone of the vehicle to attach the target to. Use `_` to select the default.

`[<pos>]`: The position (relative to the bone) to mount the target.

`[<rot>]`: The rotation (relative to the bone) to mount the target.

## History

| Version | Action        |
| ------- | ------------- |
| v3.0    | Added `/ride` |
