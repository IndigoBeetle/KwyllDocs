
# Set Tile 

## Description

![Set Tile Node](../../assets/nodes/set_tile.png){align=left width="25%"}
The *Set Tile Node* is used to set the current tile type drawn into a given
cell on the [Tilemap](../../introduction/terminology.md#tilemap) in the 
current room. 


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

Tile 
: An integer input port used to provide the tile index to change the specified
  tilemap cell to.

-------

## Parameters

X 
: A constant integer value for the X coordinate, used when the __X__ port is not
  connected.

Y 
: A constant integer value for the Y coordinate, used when the __Y__ port is not
  connected.

Tile
: A constant integer value for the tile index, used when the __Tile__port is not
  connected.

