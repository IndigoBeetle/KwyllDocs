

# Set Tile Collision

## Description

![Set Tile Collision Node](../../assets/nodes/set_tile_collision.png){align=left width="25%"}
The *Set Tile Collision Node* is used to set which sides of the given cell on the 
[Tilemap](../../introduction/terminology.md#tilemap) in the 
current room, are impenetrable. See 
[Tilemap Collision](../../introduction/backgrounds/tilemaps.md#tilemap-collision-data).


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

X 
: An integer input port used to provide the X value of the tile coordinate.

Y 
: An integer input port used to provide the Y value of the tile coordinate.

Collision 
: An integer input port used to provide collision sides to apply to the given
  cell.

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

