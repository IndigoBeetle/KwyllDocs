
# Pixel To Tile 

## Description

![Pixel To Tile Node](../../assets/nodes/pixel_to_tile.png){align=left width="25%"}
The *Pixel To Tile Node* takes input values X and Y that specify a position 
in pixel coordinates and converts them into tile coordinates.

The coordinate system of the input, room or map, is not important, the conversion
simply takes the pixel coordinate and returns the tile coordinate for the pixel
at the position, irrespective of whether it is on screen, in the room, or not.

<br style="clear:left"/>
  
-------

## Ports

X 
: An integer input port used to provide the X value of the pixel coordinate.

Y 
: An integer input port used to provide the Y value of the pixel coordinate.

*X Out*
: An integer output port that provides the converted X value in tile coordinates.

*Y Out*
: An integer output port that provides the converted Y value in tile coordinates.

-------

## Parameters

X 
: A constant integer value for the X coordinate, used when the __X__ port is not
  connected.

Y 
: A constant integer value for the Y coordinate, used when the __Y__ port is not
  connected.



