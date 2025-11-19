
# Room Types

A game in Kwyll consists of a number of locations on the
[Map](../terminology.md#map), each location represents a separate space in the
game, Kwyll does not currently support scrolling so gameplay is constrained to
a single location at a time. Each location is based on a *Room Type*, which is
in many ways equivalent to an [Object Type](../terminology.md#object-types). 

The *Room Type* is responsible for defining shared properties among all
[Locations](../terminology.md#locations) that use that *Room Type*, much like
an [Object Type](../terminology.md#object-types) defines common properties that all
[Object Instances](../terminology.md#object-instances) share. These properties 
include:

 - A [Tilemap](../terminology.md#tilemap), which represents the background of
   the room, such as the scenery, walls, platforms, etc.
 - Room [Objects](../terminology.md#object-instances), which are unique to that
   room type and are only active while the room is active.
 - Room [Logic](../terminology.md#logic) that is specific to the room type.
   Logic triggers on a Room only run when a
   [Location](../terminology.md#locations) that uses the Room is the current
   game location.
 - Markers, very lightweight objects that only contain position information, no
   sprites or logic, and are used primarily within Room or Object
   [Logic](../terminology.md#logic) to place things within a room dynamically,
   for example, a marker may be used as a spawn point for the player, or as a
   position to appear when entering a room from another room.

A *Room Type*, much like an *Object Type* doesn't actually contribute to the
game itself until it is used. A *Room Type* is used to define one or more
[Locations](../terminology.md#locations) on the [Map](../terminology.md#map). A
single *Room Type* can be used multiple times on the Map. For example, it might
be useful to create a room that has some logic on the [Room
Entered](../../logic/nodes/room_entered_trigger.md) trigger to alter how the
room looks and works using [Brushes](../terminology.md#brushes) or other logic
nodes based perhaps on variables defined in the *Room Type* and set in the
Location on the Map. This way you can place a single *Room Type* on the Map
multiple times, and change how it looks by editing the
[Variables](../terminology.md#variables) for that specific Location.

!!! note
    *Room Types* that are not placed in the [Map](../terminology.md#map) at
    all, will not be exported and will therefore not contribute to the total
    memory use of your game. This can be useful to allow you to use a *Room
    Type* as a "scratch" area, for experimenting with tiles and brushes without
    worrying about using up valuable space.
