
# For Each Tile

## Description

![For Each Tile Node](../../assets/nodes/for_each_tile.png){align=left width="25%"}
The *For Each Tile Node* is used to make changes efficiently across a
rectangular area of the [Tilemap](../../introduction/terminology.md#tilemap).


<br style="clear:left"/>
  
-------

## Ports

Flow In
: In order for this node to perform its operation, it must be connected into an
  active flow using this input port. The flow will ultimately originate at a
  __Trigger__ node but can come from the __Flow Out__ port of any other flow
  node.

Body
: A node connected to the __Body__ port will be executed in sequence for every tile
  in the rectangular area.

X 
: An integer input port used to provide the X value of the top left tile coordinate.

Y 
: An integer input port used to provide the Y value of the top left tile coordinate.

X 
: An integer input port used to provide the width in tiles of the area to process.

H 
: An integer input port used to provide the height in tiles of the area to process.

*X Out*
: An integer output port, used to provide the X tile coordinate to the __Body__ flow,
  each iteration through the loop, this value is updated to represent the current tile
  in the area.

*Y Out*
: An integer output port, used to provide the Y tile coordinate to the __Body__ flow,
  each iteration through the loop, this value is updated to represent the current tile
  in the area.

Exit
: A node connected to the __Exit__ port will be executed in sequence
  following the completion of this node's operation.


-------

## Parameters

X 
: A constant integer value for the X coordinate, used when the __X__ port is not
  connected.

Y 
: A constant integer value for the Y coordinate, used when the __Y__ port is not
  connected.

Collision
: A constant value for the collision sides, used when the __Collision__ port is
  not connected.


