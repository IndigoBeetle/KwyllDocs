# Terminology

There are several stages to developing a game with Kwyll, each with
their own section in the tool. Below is a short introduction to some of
the terminology that you will come across frequently throughout this
documentation, this is a good place to start to ensure that you have the
best chance of understanding what is being described later in the guide.

## Sprites

Of course, any game needs some graphics, right? In Kwyll there are two main
places you can draw pixel graphics, Sprites, and Tiles. A Sprite in Kwyll is a
rectangular grid of pixels, Sprites can be various sizes, always in increments
of 8 pixels in both axes. So, for example, 8x8, 16x16, 8x16, etc. An arbitrary
limit is placed on the maximum size of 32 in either axis just to keep things
within reason for the target platforms to maintain performance and limit memory
use. See [Sprites](objects/sprites.md) for more details.


## Tiles

Tiles are the simpler, more constrained, cousin to Sprites. They are also
simple grid of pixels, however, a Tile is always 8x8 (unless a particular
platform supports or requires a different size), and cannot be used in [Object
Types](#object-types), instead they are used in [Rooms Types](#room-types),
typically to draw the background of a room, over which an
[Object's](#object-instances) Sprites are drawn, and [Screens](#screens), for
example to draw borders or background graphics for a screen be it a menu
screen. Tiles can also as the used in an [Instrument](#instruments) of the
right type to show graphics instead of simple text or numbers.


## Tilemap

In the [Room Editor](../interface/room_editor.md) and the 
[Screen Editor](../interface/screen_editor.md) you can use Tiles to draw what
is referred to in Kwyll as a Tilemap. This is an efficient way to draw lots
of graphics in Kwyll. For [Rooms Types](#room-types), this is typically used to draw the 
background of your game. The [Screen](#screens) tilemap is often used to create
a surround for your game window, something in which to place the instruments.


## Brushes

Brushes allow you to optimise your background designs, specifically where there
are sections of your backgrounds that are used frequently. Using brushes you
can store a rectangle of tile information and repeatedly apply it to your
[Tilemap](#tilemap) very cheaply to maximise the available space for your game.
See [Brushes](backgrounds/brushes.md) for more details.



## Object Types

An Object in Kwyll is a type of thing that can be displayed on screen and
respond in various ways to the input of the player or to game logic. Objects
are the heart of any Kwyll game, without Objects, the game wouldn't actually do
anything, making for a very dull game. See [Object Types](objects/object_types.md)
for more details.


## Object Instances

An *Object Type* does not contribute to the game iself, it has to be used.
Object instances can be created in Rooms and the Map, each instance shares the
visual representation and logic code from the *Object Type*, but each use has
its own position, values for the variables defined in the logic, [Timeline
Animations](#timeline-animation), flags, and any other information that might
be specific to a particular platform. See [Object
Instances](objects/object_instances.md) for more details.


## Room Types

A Room in Kwyll is the definition of a space in which part, or all, of your game
takes place. Much like [Object Types](#object-types), they do not exist in the
game on their own, they are used as [Locations](#locations) on the [Map](#map).


## Timeline Animation

Objects added to [Room Types](#room-types) can be animated using a simple
keyframe system. Keyframes can be placed at certain times on a timeline that
define the position of that object at that point in time, and Kwyll will
interpolate smoothly betwen the keyframes over time, allowing you to create
smooth animations that are very cost effective in terms of memory use. This is
useful for enemies that follow a path for instance. See [Timeline
Animations](locations/timeline_animation.md) for more details.


## Locations

Just as with *Object Types*, a *Room Type* needs to be used in your game for it
to have any value. A *Location* is a use of a *Room Type* on the [Map](#map). A
*Location* is equivalent to an *Object Instance*, each location shares the
tilemap, logic, markers and room objects with any other location that uses the
same *Room Type*. However, each location has its own name, default colour
information, and variable values. See [Locations](locations/locations.md) for
more details.


## Map

The *Map* is where you place *Room Types* and arrange them to create your game's 
map. See the [Map Editor](../interface/map_editor.md) for more information about
creating your game map.


## Screens

A *Screen* in Kwyll displays a collection of elements including
[Instruments](#instruments), a [Tilemap](#tilemap), and the game window, that
can be used for different things in your game, such as a menu, help screen, the
game screen and many more. See [Screens](screens/screens.md) for more details.


## Instruments

*Instruments* are display elements that can be used in [Screens](#screens) to
display various information about your game. They are used to present
information to the player about the game, such as score, lives etc. See
[Instruments](screens/instruments.md) for more details.


## Logic

In a Kwyll game, much of the way a game plays is controlled by the game *Logic*.
Kwyll provides a node based system for creating logic that is easy to 
use and provides a more visual approach to programming than typical text based
programming languages. See [Logic](logic/logic.md) for more details.


## Variables

Variables are values that can be registered anywhere [Logic](#logic) is used to
both store data during the game, and to allow configuration of the things that
use the logic as part of the game data. See [Variables](logic/variables.md) for
more details.


## Data

In Kwyll, the *Data* section allows the game designer to define a fixed set of
text strings to use in the game. These are typically used to display in
instruments using the *Text* instrument type.


## Input/Output

Player input in Kwyll is entirely managed by the [logic](#logic) system, the 
game designer is responsible for querying the input using the relevant nodes
and responding to that input using the wealth of other logic nodes available.

Input is handled in one of two ways, via the [Controller
Input](../logic/nodes/controller.md) node, which is designed to provide common
left, right, up, down and fire type controls common to many games, and the [Key
Input](../logic/nodes/key_input.md) node, which is for more flexible checking
of any key.


## Controller

The [Controller Input](../logic/nodes/controller.md) node can read input from
either the defined control keys, which can be customised in the project
settings and updated at runtime using the [Configure
Controller](../logic/nodes/configure_controller.md) node, allowing your player
to redifine their preferred keys for left, right, up, down and fire.


## Key Input

The [Key Input](../logic/nodes/key_input.md) node can be used to check for
specific keys not used as part of the controller. It can also be used to
check for "any" key, if all that matters is the player presses a key to 
start the game for example.


## Keycodes

In Kwyll keys are identified using an internal keycode system that can be
adapted for use on various different target platforms. See
[Keycodes](io/keycodes.md) for more details.

## Colour
