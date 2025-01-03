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

It is important to know that a Sprite doesn't actually 'do' anything in
Kwyll, it's just an image, it has no position, it isn't by default drawn
to the screen anywhere, in order to get a Sprite onto the screen, it
must be used by an Object.

## Objects

An Object in Kwyll is a type of thing that can be displayed on screen
and respond in various ways to the input of the player or to game
logic that is defined in Kwyll. Objects are the heart of any Kwyll
game, without Objects, the game wouldn't actually do anything, making
for a very dull game. 

An Object must first be *defined*, the definition of an Object details things
like the visual represenation via [Sprites](#sprites) and any other information
that is required to display the object that may be platform specific, such as
colour and draw mode, and any [Logic](#logic). To use an Object in your game
requires creating *Object References* or *Refs*. These are instances of the
object definition, they share the visual representation and logic code that the
*Object Definition* holds, but each *Ref* has it's own position, logic
variables, [Timeline Animations](#timeline-animation), and any other
information that might be specific to a particular platform. *Object
References* can be created in the following ways.

 - Global Objects - these are created in the [Map
   Editor](../interface/map_editor.md) and are constant throughout the game,
   they will always exist irrespective of which [Location](#locations) you are
   in, and will be drawn, if their position puts them on screen, and their
   logic will be executed.
 - Local or Room Objects - these are in each [Room Definition](#rooms) and will
   only be active while in a [Location](#locations) that references that room,
   so they will not be drawn or their logic executed when in another room. It's
   worth noting that when exiting a room that contains Room Objects, the data
   used by the Kwyll library for those objects, such as memory for
   [Sprite](#sprites) rendering etc. will be freed, reducing the overhead for
   both memory and performance, so it is advisable to use Room Objects where
   appropriate over Global Objects.
 - Dynamic Objects - these are not created in an editor during your game
   creation, they are instead created during the game using the [Spawn
   Object](../logic/nodes/spawn_object.md) node, and can be destroyed using the
   [Kill Object](../logic/nodes/kill_object.md) node. They are in all other
   respects similar to Global Objects, they are not constrained to a particular
   [Room](#rooms), and will continue to exist across changes in
   [Location](#locations) until they are destroyed.

An *Object Definition* consists of two main elements.

 - Animations, which are sequences of [Sprite](#sprites) images played in order
   to create the illusion of animation. Each object can have many Animations,
   for example, a player object might have an animation for walking left, one
   for walking right, one for jumping, one for attacking etc. The game designer
   can choose which Animation is played using the logic nodes based on what is
   happening in the game at that moment.
 - [Logic](#logic) is the "brains" of an Object, it defines what an Object
   does, and when. In Kwyll, logic is created using a visual programming tool
   that we'll get into later, a powerful means of writing code without writing
   code.

## Tiles

Tiles are the simpler, more constrained, cousin to Sprites. They are also
simple grid of pixels, however, a Tile is always 8x8, and cannot be used in
[Objects](#objects), instead they are used in [Rooms](#rooms), typically to
draw the background of a room, over which an Object's Sprites are drawn, and
Screens, typically to draw borders or background graphics for a screen be it a
menu screen, a game screen or any other use.

Unlike Sprites, Tiles do not have their own separate editor in Kwyll, the tools
to create, edit and modify Tiles are integrated into the Room and Screen
editors, as they are simple and it is convenient to have their editing tools in
place in the editors where you use tiles. This choice means it's very efficient
to work with Tiles when drawing your [Rooms](#rooms) and Screens, with all the
tools you need in one place.

## Rooms

A game in Kwyll consists of a number of 'rooms', each room represents a
separate space in the game, Kwyll does not currently support scrolling so
gameplay is constrained to a single screen at a time, rooms allow you to move
between these spaces. Each room contains any combination of the following
elements:

 - A Tilemap, which represents the background of the room, such as the scenery,
   walls, platforms, etc.
 - Room [Objects](#objects), which are unique to that room definition and are
   only active while the room is active.
 - Room [Logic](#logic) that is specific to the room defintion, the Always
   triggers on Room Logic are only executed while the room is active.
 - Markers, very lightweight objects that only contain position information, no
   sprites or logic, and are used primarily within Room or Object
   [Logic](#logic) to place things within a room dynamically, for example, a
   marker may be used as a spawn point for the player, or as a position to
   appear when entering a room from another room.


## Screens


## Logic


## Timeline Animation


## Locations
