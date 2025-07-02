
# Modify Tiles

## Description

![Modify Tiles Node](../../assets/nodes/modify_tiles.png){align=left width="25%"}
The *Modify Tiles Node* replaces information in the current location tilemap
over a rectangular area with a single value. It is typically used to change 
colour or collision information of a region, but can also be used to change
the tiles in use, although the entire region would get the same tile.

The *Modify Tiles Node* is a little different to many other nodes in the way
it presents parameters, this is due to the fact that it can be used to modify 
only certain properties of the tilemap. The primary difference in the 
parameters is the inclusion of an additional checkbox for each with a small 
__X__ above it, this check box is used to indicate that the operation should
ignore that property altogether. For example, selecting the __X__ checkbox
on the __Collision__ property would ensure that the operation makes no 
changes at all to the collision information in the areas specified.

<br style="clear:left"/>
  
-------

## Ports

Flow In
: In order for this node to perform its operation, it must be connected into an
  active flow using this input port. The flow will ultimately originate at a
  __Trigger__ node but can come from the __Flow Out__ port of any other flow
  node.

Flow Out
: A node connected to the __Flow Out__ port will be executed in sequence
  following the completion of this node's operation.

X1 
: An integer input port used to provide the X value of the top left corner
  of the area to be updated, in tile coordinates.

Y1 
: An integer input port used to provide the Y value of the top left corner
  of the area to be updated, in tile coordinates.

X2 
: An integer input port used to provide the X value of the bottom right corner
  of the area to be updated, in tile coordinates.

Y2 
: An integer input port used to provide the Y value of the bottom right corner
  of the area to be updated, in tile coordinates.

Tile
: An integer input port used to provide the index of the tile to place in all
  tilemap cells in the specified region. See the parameter description below
  for more detail.

Collision
: An integer input port used to provide the bit field information for the collision
  of the tilemap cells in the specified region. See the parameter description below
  for more detail.

Ink
: An integer input port used to provide the ink colour of the tilemap cells in the 
  specified region. See the parameter description below for more detail.

Paper
: An integer input port used to provide the paper colour of the tilemap cells in the 
  specified region. See the parameter description below for more detail.

Bright
: An integer input port used to provide the bright setting of the tilemap cells in the 
  specified region. See the parameter description below for more detail.

-------

## Parameters

X1 
: A constant integer value for the X1 coordinate, used when the __X1__ port is not
  connected.

Y1 
: A constant integer value for the Y1 coordinate, used when the __Y1__ port is not
  connected.

X2 
: A constant integer value for the X2 coordinate, used when the __X1__ port is not
  connected.

Y2 
: A constant integer value for the Y2 coordinate, used when the __Y1__ port is not
  connected.

Tile
: A constant integer value to specify the tile to use, the preview to the right of the
  numerical value will update to show the chosen tile. The checkbox with the trashcan
  above indicates that the tile should be removed, not replaced. The checkbox with the 
  __X__ above indicates that the tile should not be changed.

Collision
: Four checkboxes indicate whether the tiles will have collision enabled in the up
  down, left or right directions. The checkbox with the __X__ above indicates that 
  the tile collision information should not be changed.

Ink
: A colour selector to choose visually the ink colour to use for the tiles. The checkbox
  with the __X__ above indicates that the ink colour of the tiles should not be changed.

Paper
: A colour selector to choose visually the paper colour to use for the tiles. The checkbox
  with the __X__ above indicates that the paper colour of the tiles should not be changed.

Bright
: A checkbox to select whether the tiles will be bright or not. The checkbox
  with the __X__ above indicates that the brightness of the tiles should not be changed.
