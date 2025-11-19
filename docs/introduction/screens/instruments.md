
# Instruments

*Instruments* are display elements that can be used in
[Screens](../terminology.md#screens) to display various information about your
game. An instrument can be one of 4 types:

 - Integer, a simple numerical value.
 - Text, a fixed text string from the list of options defined in the 
   [Data](../terminology.md#data) section.
 - Tile, the graphic for a specific tile from the tile set defined in the 
   [Screen Editor](../../interface/screen_editor.md) or 
   [Room Editor](../../interface/room_editor.md).
 - Keycode, displays the key name for a particular keyboard scancode.

Each instrument has a position in the same grid as the tile map, that is, it is
constrained to 8x8 pixel positions, you cannot place an instrument with pixel
accuracy. Each instrument can also optionally have its own colour information,
if not provided, the instrument will take on the colour settings from the 
[Screen](../terminology.md#screens).

The *value* of an instrument is always a 16 bit numerical value. How this value
is interpreted to produce the display depends on the type of instrument:

 - Integer, the value is displayed in base 10.
 - Text, the value is the index of a text string in the strings list defined in
   the [Data](../terminology.md#data) section.
 - Tile, the value is the index of a tile in the tile set, you can determin what
   each tile's index is by looking at the tile set in the 
   [Screen Editor](../../interface/screen_editor.md) or 
   [Room Editor](../../interface/room_editor.md), the white (leftmost) number below
   the tile image is the index.
 - Keycode, the value is converted from a key
   [Keycode](../terminology.md#keycodes) to a key name as text, for example,
   1792 will display "SPACE".

You can modify the value of an instrument during the game using the 
[Set Instrument](../../logic/nodes/set_instrument_value.md) node.

