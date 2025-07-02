
# Map To Location 

## Description

![Map To Location Node](../../assets/nodes/map_to_location.png){align=left width="25%"}
The *Map To Location Node* takes input values X and Y that define a position 
in map coordinates  and converts the position to the room coordinates of a specified 
[Location](../../introduction/terminology.md#locations).

This is particularly useful for positioning a room level object so that it is at a chosen
position on the map, presuming the position is within the bounds of the location.

<br style="clear:left"/>
  
-------

## Ports

Location 
: A location reference port that provides a reference to the location that the
  resulting coordinates are relative to. If not connected, and the logic is on
  a location, the current location will be used.

X 
: An integer input port used to provide the X value of the map coordinate.

Y 
: An integer input port used to provide the Y value of the map coordinate.


-------

## Parameters

X 
: A constant integer value for the X coordinate, used when the __X__ port is not
  connected.

Y 
: A constant integer value for the Y coordinate, used when the __Y__ port is not
  connected.


