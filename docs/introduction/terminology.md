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
colour and draw mode, and any [Logic](#logic). 

However, an *Object Definition* does not contribute to the game iself, it has to
be used. Objects can be used in Rooms and the Map, each use shares the visual
representation and logic code from the *Object Definition*, but each use 
has its own position, values for the variables defined in the logic, [Timeline
Animations](#timeline-animation), flags, and any other information that might be
specific to a particular platform. Each use of a defined object is called an
*Object Instance*.  

Objects can be used in the following ways.

 - Map Objects - these are created in the [Map
   Editor](../interface/map_editor.md) and are constant throughout the game,
   they will always exist irrespective of which [Location](#locations) you are
   in, and will be drawn, if their position puts them on screen, and their logic
   will be run.
 - Room Objects - these are in each [Room Definition](#rooms) and will only be
   active while in a [Location](#locations) that uses that Room, so they will
   not be drawn or their logic run when in location that uses another room.
   It's worth noting that when exiting a room that contains Room Objects, the
   data used by the Kwyll library for those objects, such as memory for
   [Sprite](#sprites) etc. will be freed, reducing the overhead for
   both memory and performance, so it is advisable to use Room Objects where
   appropriate over Map Objects.
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
 - [Logic](#logic) is the "brains" of an Object, it defines what an Object does,
   and when. In Kwyll, logic is created using a visual programming tool, a
   powerful means of writing code without writing code.

## Tiles

Tiles are the simpler, more constrained, cousin to Sprites. They are also simple
grid of pixels, however, a Tile is always 8x8 (unless a particular platform
supports or requires a different size), and cannot be used in
[Objects](#objects), instead they are used in [Rooms](#rooms), typically to draw
the background of a room, over which an [Object's](#objects) Sprites are drawn,
and [Screens](#screens), typically to draw borders or background graphics for a
screen be it a menu screen, a game screen or any other use, and also as the
content of an [Instrument](#instrument) of the appropriate type.


## Tilemap


## Rooms

A game in Kwyll consists of a number of Rooms, each room represents a
separate space in the game, Kwyll does not currently support scrolling so
gameplay is constrained to a single screen at a time, rooms allow you to move
between these spaces. Each Room contains any combination of the following
elements:

 - A Tilemap, which represents the background of the room, such as the scenery,
   walls, platforms, etc.
 - Room [Objects](#objects), which are unique to that room definition and are
   only active while the room is active.
 - Room [Logic](#logic) that is specific to the room defintion. Logic triggers
   on a Room only run when a [Location](#locations) that uses the Room is the
   current game location.
 - Markers, very lightweight objects that only contain position information, no
   sprites or logic, and are used primarily within Room or Object
   [Logic](#logic) to place things within a room dynamically, for example, a
   marker may be used as a spawn point for the player, or as a position to
   appear when entering a room from another room.

A *Room Defintion*, much like an *Object Definition* doesn't actually contribute
to the game itself until it is used, in the case of a Room, the definition has
to be used in the [Map](#map) in a [Location](#locations). The [Map](#map) can
contain multiple [Locations](#locations) that use the same *Room Definition*,
much like an *Object Definition* can be used multiple times for Room and Map
objects.


## Screens

A Screen in Kwyll is a collection of [Instruments](#instruments), a Tilemap, and
optionally, the game window. A screen can also have [Logic](#logic) associated
with it that is run while that screen is the current screen. 

There is only one screen active at any time in a Kwyll game. Uses of screens
include the main game screen which will have the game window positioned on the
screen accordingly, a menu screen, instructions, and many others.


## Instruments


## Logic

In a Kwyll game, much of the way a game plays is controlled by the game *Logic*.
Kwyll provides a node based system for creating logic that is easy to 
use and provides a more visual approach to programming than typical text based
programming languages. It is described in more detail in the 
[Logic](../logic/intro.md) section of this manual. 

Logic can be used in various places in a kwyll game allowing lots of flexibility
in how you structure your game. 

### Object Logic

Each [Object Definition](#objects) can have *Logic* assigned to it, this
logic is shared with each *Object Instance* that uses the definition, allowing
you to very efficiently define behaviour that is shared among many objects. 
Object logic only runs for objects that are currently active, that includes any
[Map](#map) level objects which are global and active all the time, any dynamic
objects, and any room objects for the current location only.

### Room Logic

Each [Room Definition](#rooms) can have *Logic* assigned to it in the same way
as an [Object Definition](#objects). Each [Location](#locations) that uses the
room definition shares the logic in the same way an [Object Instance](#objects)
does. Room logic only runs for the current [Location](#locations).

### Screen Logic

Each [Screen](#screens) can have *Logic* assigned to it, this is typically used 
to manage the elements in the screen, primarily the instruments. Screen logic 
only runs for the current screen.

### Global Logic

In addition to each of the individual locations listed above, a Kwyll game can 
have some global logic that will execute all the time irrespective of location
and screen.

### Shared Logic

Each of the logic locations listed above are potentially active logic sections,
that means that Kwyll will run certain flows on them at the appropriate time, 
for example the [Always](../logic/nodes/always.md) flows will run ever frame,
the [Object Hit](../logic/nodes/object_hit.md) flows will run when an object
intersection is detected. Shared logic is different. It offers a means to 
created sections of logic that can be reused, effectively creating custom nodes.
Shared logic consists of *Subgraphs* which are equivalent to subroutines in 
many common programming languages. They can take an arbitrary number of inputs
and output an arbitrary number of results.

Subgraphs are a very powerful concept in Kwyll that gives both the ability to
optimise and streamline your logic creation with custom nodes, and share those
custom nodes with others.


## Timeline Animation


## Locations


## Data
