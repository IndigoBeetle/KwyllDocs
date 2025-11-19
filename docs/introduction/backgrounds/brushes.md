
# Brushes

In addition to drawing tiles, attributes (colours) and collision information
directly into the tilemap, another tool available in Kwyll for drawing the
content of tilemaps is the __Brush__. A brush consists of a separate record
of tile, attribute and collision information stored within the game that can
be placed any number of times into a tilemap very cheaply. See the
[Tilemap Editor](../../interface/tilemap_editor.md) section for details of how 
to create and use Brushes. Brushes are a very efficient way to create tilemaps
that have lots of repeated sections. Drawing each individual tile is more
expensive than storing the repeated sections in a Brush and just pasting the
Brush multiple times. A Brush can be any width or height in tiles, not pixels.

See the [Tilemap Editor](../../interface/tilemap_editor.md) section for
information about how to create and use Brushes.
