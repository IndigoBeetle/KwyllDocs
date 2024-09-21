# Terminology

There are several stages to developing a game with Kwyll, each with
their own section in the tool. Below is a short introduction to some of
the terminology that you will come across frequently throughout this
documentation, this is a good place to start to ensure that you have the
best chance of understanding what is being described later in the guide.

## Sprites

Of course, any game needs some graphics, right? In Kwyll there are two
main places you can draw pixel graphics, Sprites, and Tiles. A Sprite in
Kwyll is a rectangular grid of pixels, Sprites can be various sizes,
always in increments of 8 pixels in both axes. So, for example, 8x8,
16x16, 8x16, etc. An arbitrary limit is placed on the maximum size of 32
in either axis just to keep things within reason for the target
platforms to maintain performance and limit memory use. 

It is important to know that a Sprite doesn't actually "do" anything in
Kwyll, it's just an image, it has no position, it isn't by default drawn
to the screen anywhere, in order to get a Sprite onto the screen, it
must be used by an Object.

## Objects

An Object in Kwyll is a type of thing that can be displayed on screen
and respond in various ways to the input of the player or to game
logic that is defined in Kwyll. Objects are the heart of any Kwyll
game, without Objects, the game wouldn't actually do anything, making
for a very dull game.

An Object consists of two main elements.

 - Animations, which are sequences of Sprite images played in order to
   create the illusion of animation. Each object can have many
   Animations, for example, a player object might have an animation for
   walking left, one for walking right, one for jumping, one for
   attacking etc. The game designer can choose which Animation is played
   using the logic nodes based on what is happening in the game at that
   moment.
 - Logic is the "brains" of an Object, it defines what an Object does,
   and when. In Kwyll, logic is created using a visual programming tool
   that we'll get into later, a powerful means of writing code without
   writing code.

## Tiles

Tiles are the simpler, more constrained, cousin to Sprites. They are
also simple grid of pixels, however, a Tile is always 8x8, and cannot be
used in Objects, instead they are used in Rooms, typically to draw the
background of a room, over which an Object's Sprites are drawn.

Unlike Sprites, Tiles do not have their own separate editor in Kwyll,
the tools to create, edit and modify Tiles are integrated into the Room
editor, as they are simple and this is the only place they can be used.
This choice means it's very efficient to work with Tiles when drawing
your Rooms, with all the tools you need in one place.

