# Data types

## String

Any single word (whitespace at the beginning and end is ignored)

#### Examples:

`hi`

`ThePython10110`

`better_commands`

## Long string

Any text (whitespace at the beginnning and end is ignored). Long strings are _always_ the last argument in a command.

#### Examples:

`example`

`another example`

`12983 plus eighty-nine =     thirteen thousand and 72`

## Number

Any positive or negative number from -99,999,999,999,999 (negative 100 trillion + 1**)** to 100,000,000,000,000. (100 trillion)

#### Examples:

`1`

`3.141592`

`-65535`

## Boolean

Either `true` or `false`.

## Position

A position is a set of three values intended to be used as x, y, and z coordinates (in that order).

#### Axes:

* North: +Z (note that in ACOVG, north and south are reversed)
* South: -Z
* East: +X
* West: -X
* Up: +Y
* Down: -Y

There are three possible value types that can be used as coordinates:

### Absolute coordinates (numbers)

Absolute coordinates are used to specify an exact position in the world. They are just numbers.

#### Examples

`1 50 7` means the position {x=1, y=50, z=7}.

`-23.52 38.8 0` means the position {x=-23.52, y=38.8, z=0}

### Relative coordinates (tilde notation)

Relative coordinates are used to specify a coordinate relative to where the command is executed. Relative coordinates are preceded by a tilde (\~). You can combine relative coordinates with absolute coordinates.

#### Examples

`~ ~5 ~` means the position 5 nodes above the execution position.

`~-2 ~ 25` means the position 2 nodes in the -X direction from the execution position, with the Z coordinate replaced with 25. At {x=3, y=5, z=-3.5}, this would evaluate to {x=1, y=5, z=25}.

### Local coordinates (caret notation)

Local coordinates are used to specify a coordinate relative to the execution position and rotation. It's similar to relative coordinates, except the execution rotation is treated as the Z-axis. Local coordinates are preceded with a caret (^). You _**cannot**_ combine local coordinates with absolute or relative coordinates.

#### Examples

`^ ^ ^5` Five nodes "forward"

`^ ^-5 ^` Five nodes "down"

`^-2 ^ ^` Two nodes "left"

## Rotation

One or two values, intended to be used as yaw (left/right rotation) and sometimes pitch (up/down rotation). Values are in degrees, and support tilde (relative) notation.

#### Directions

* North: Yaw = 0
* West: Yaw = 90
* South: Yaw = 180
* East: Yaw = 270
* Up: Pitch = 90 (maximum for players is 89.5)
* Down: Pitch = -90 (minimum for players is -89.5)

#### Examples

`45`: Northwest

`~45`: 45 degrees counterclockwise from the current direction

`180 -90`: Facing south and down

`~1 ~-1` (1 degree counterclockwise and one degree up from the current direction)



## Selector

See [Target Selectors](target-selectors.md).

