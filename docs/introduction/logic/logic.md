
# Logic

In a Kwyll game, much of the way a game plays is controlled by the game *Logic*.
Kwyll provides a node based system for creating logic that is easy to 
use and provides a more visual approach to programming than typical text based
programming languages. It is described in more detail in the 
[Logic](../../logic/intro.md) section of this manual. 

Logic can be used in various places in a kwyll game allowing lots of flexibility
in how you structure your game. 

### Object Logic

Each [Object Type](../terminology.md#object-types) can have *Logic* assigned to
it, this logic is shared with each *Object Instance* that uses the definition,
allowing you to very efficiently define behaviour that is shared among many
objects. Object logic only runs for objects that are currently active, that
includes any [Map](../terminology.md#map) level objects which are global and
active all the time, any dynamic objects, and any room objects for the current
location only.

### Room Logic

Each [Room Type](../terminology.md#room-types) can have *Logic* assigned to it
in the same way as an [Object Type](../terminology.md#object-types). Each
[Location](../terminology.md#locations) that uses the room definition shares
the logic in the same way an [Object
Instance](../terminology.md#object-instances) does. Room logic only runs for
the current [Location](../terminology.md#locations).

### Screen Logic

Each [Screen](../terminology.md#screens) can have
[Logic](../terminology.md#logic) assigned to it, this is typically used to
manage the elements in the screen, primarily the instruments. Screen logic only
runs for the current screen.

### Global Logic

In addition to each of the individual locations listed above, a Kwyll game can 
have some global logic that will execute all the time irrespective of location
and screen.

### Shared Logic

Each of the logic locations listed above are potentially active logic sections,
that means that Kwyll will run certain flows on them at the appropriate time, 
for example the [Always](../../logic/nodes/always.md) flows will run ever frame,
the [Object Hit](../../logic/nodes/object_hit.md) flows will run when an object
intersection is detected. Shared logic is different. It offers a means to 
created sections of logic that can be reused, effectively creating custom nodes.
Shared logic consists of *Subgraphs* which are equivalent to subroutines in 
many common programming languages. They can take an arbitrary number of inputs
and output an arbitrary number of results.

Subgraphs are a very powerful concept in Kwyll that gives both the ability to
optimise and streamline your logic creation with custom nodes, and share those
custom nodes with others.

