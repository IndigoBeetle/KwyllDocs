
# Marker Position

## Description

![Marker Position Node](../../assets/nodes/marker_position.png){align=left width="25%"}
The *Marker Position Node* queries the position of a 
[Marker](../../introduction/terminology.md#room-types) in a given location, returning
the position in room coordinates.

<br style="clear:left"/>
  
-------

## Ports

Location 
: A location reference port that provides a reference to the location that the
  provided coordinates are relative to. If not connected, and the logic is on
  a location, the current location will be used.

Marker
: An integer input port that provides the index of the marker to query.

X 
: An integer output port that provides the X value of the marker coordinate.

Y 
: An integer output port that provides the Y value of the marker coordinate.


-------

## Parameters

Marker 
: A constant integer value for the marker index, used when the __Marker__ port is not
  connected.


