# Sprites

Of course, any game needs some graphics, right? In Kwyll there are two
main places you can draw pixel graphics, Sprites, and Tiles. A Sprite in
Kwyll is a rectangular grid of pixels, Sprites can be various sizes,
always in increments of 8 pixels in both axes. So, for example, 8x8,
16x16, 8x16, etc. An arbitrary limit is placed on the maximum size of 32
in either axis just to keep things within reason for the target
platforms to maintain performance and limit memory use. 

It is important to know that a Sprite doesn't actually 'do' anything in
Kwyll, it's just an image, it has no position, it isn't by default drawn
to the screen anywhere, in order to get a Sprite onto the screen, it
must be used by an __Object__.

## Draw Modes

When assigned to an __Object__, the object can choose which mode to use to
draw the __Sprite__ to the screen, which is best depends on the particular
use case in your game. The optons are:

LOAD
: The sprite is just placed into each 8x8 cell that it touches, completely
  overwriting anything that might already be there in the 
  [Tilemap](../backgrounds/tilemaps.md) or any other __Objects__.
  This is normally only used if you know there will be no background where
  the object is used.
  This is the fastes sprite rendering mode.

OR/XOR
: These two modes combine the pixels of the __Sprite__ with those in the
  background using bitwise OR and XOR operations. The result is that the 
  background isn't completely wiped out in 8x8 blocks like LOAD mode, but
  depending on the nature of the __Sprite__ and the tiled background, can 
  result in objects becoming difficult to see.

MASK
: This requires that a __Sprite__ is defined with a "Mask" layer, see the
  [Sprite Editor](../../interface/sprite_editor.md) for details of creating 
  mask layers. This mode clears a part of the background in a user defined
  shape before drawing the sprite pixels into that space. It is the most
  effective draw mode, resulting in well defined pixels that can be easily
  distinguished from the background, but is the most costly in terms of 
  both memory use, requiring additional data for each __Sprite__, and in
  terms of performance.




## Planes

When a __Sprite__ is drawn to the screen it is possible that there will be
other sprites in the same place on the screen, so there has to be a way to
decide which one is drawn first. This is the role of planes. Think of planes as
"layers", with the smallest number being closest to the screen, and increasing
numbers going further away. So an __Object__ that has its plane set to 1, will
have its sprites drawn over the top of another __Object__ that has its plane
set to 2, which in turn will drawn over another __Object__ that has its plane
set to 5. This feature may be platform specific, check the details for your
platform for details.

