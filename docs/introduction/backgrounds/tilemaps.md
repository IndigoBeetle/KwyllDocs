
# Tilemaps

In the [Room Editor](../../interface/room_editor.md) and the [Screen
Editor](../../interface/screen_editor.md) you can use Tiles to draw what is
referred to in Kwyll as a Tilemap. This is an efficient way to draw lots of
graphics in Kwyll. For [Rooms Types](../terminology.md#room-types), this is
typically used to draw the background of your game. The
[Screen](../terminology.md#screens) tilemap is often used to create a surround
for your game window, something in which to place the instruments.

Both the [Room](../terminology.md#room-types) and
[Screen](../terminology.md#screens) tilemaps store a tile type and colour
information for each grid cell in the tile map. The grid size is defined by the
__Window__ game setting for [Room Types](../terminology.md#room-types), and is
the entire size of the screen for [Screens](../terminology.md#screens). It
should be noted however, that in a [Screen](../terminology.md#screens) that is
defined as a Game Screen, and shows the game window, it is not possible to draw
tiles in the area occupied by the game screen, they will be overridden by the
game display.

### Tilemap Collision Data

[Room Types](../terminology.md#room-types) also have an additional feature
stored in their tilemaps that is specific to gameplay and not appropriate for
[Screens](../terminology.md#screens), collision data. This stores information
about how objects can or cannot pass through a particular grid cell. It's
possible to define each grid cell to allow or prevent movement through it in
all 4 directions independently. For example, a grid cell can be configured to
allow an object to pass through safely when travelling up the screen, but to
prevent it passing through when travelling down the screen, something often
used in platformer games for the platforms.


