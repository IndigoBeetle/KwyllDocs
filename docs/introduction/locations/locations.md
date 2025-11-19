
# Locations

Just as with *Object Types*, a *Room Type* needs to be used in your game for it
to have any value. A *Location* is a use of a *Room Type* on the
[Map](../terminology.md#map). A *Location* is equivalent to an *Object
Instance*, each location shares the tilemap, logic, markers and room objects
with any other location that uses the same *Room Type*. However, each location
has its own name, default colour information, and variable values. 

Changing a variable value in room [logic](../terminology.md#logic) changes the
value on the particular location that is running the logic. For example,
imagine you have a forest *Room Type* with some logic that includes a variable
"south door", which is 1 if the south door is closed, and 0 if it is open, and
in the logic for that *Room Type* you paste a brush in the south doorway, an
open door if it is open, a closed door if it is closed. If you create two
locations using that *Room Type*, each location will have its own value for the
"south door" variable, when something happens to open the door in the first of
those two locations, the value of the "south door" variable is updated, and the
shared logic changes the display of the door, it is modifying only the value
stored on the first location, the value on the second location is not changed.
Similarly, when the player opens the south door in the second location, the
"south door" variable on the second location is changed, and the first
location's "south door" value remains unchanged.
