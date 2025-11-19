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

