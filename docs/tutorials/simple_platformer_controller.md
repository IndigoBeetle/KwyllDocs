# Simple Platformer Controller

## How To Create A Simple, Left, Right and Jump Platformer Controller

One of the most common game genres for retro computers is the platformer, a
game where the player typically has controls to move left and right, and to
jump onto platforms and fall down when walking off a platform. This tutorial
guides you through creating the logic nodes to create a player object in this
style. While this very likely won't be adequate for a fully fledged game it
should give some insights into some of the techniques that Kwyll offers to do
this and serve as a starting point for customisation and improvement.

## Setup

### Sprite

First, lets start by creating a sprite for our character, something simple as
we're not focused on animation for this tutorial.

![Player Sprite](../assets/tutorials/simple_platformer_controller/player_sprite.png)


### Object

Then we'll turn this sprite into a simple object, our Player, remember to name
it appropriately and set the draw mode to mask if you've drawn a mask for your
player sprite. Add a single animation with one frame and choose the sprite you
created for your character.

![Player Object](../assets/tutorials/simple_platformer_controller/player_object.png)


### Room

Next we'll setup a simple room to test out the player. Create a single simple
tile, in the properties dialog, make sure to set the default collision to "top"
as this will be the tile for our platforms, we want to be able to jump up
through it, but then land on the top and not fall through.

![Tile](../assets/tutorials/simple_platformer_controller/tile.png)

Draw a ground and some platforms for our player to jump on using the tile we
just created.

![Room](../assets/tutorials/simple_platformer_controller/room.png)

Drag the Player object from the objects panel onto the room. Note: normally
the player would be a "Map" object, which allows it to travel between rooms,
but for the purposes of this tutorial, we'll just have a single room, so we can
just place our player in the room directly. 


![Player In Room](../assets/tutorials/simple_platformer_controller/player_in_room.png)

Once placed, open the object properties dialog and make sure the "Collide Bg"
flag is set so that the player object will collide with our platform tiles.

![Player Object Flags](../assets/tutorials/simple_platformer_controller/player_object_flags.png)


### Map

Finally, in order to be able to play the game, we must add the room to the map.

![Map](../assets/tutorials/simple_platformer_controller/map.png)


## Logic

Now that we've got all the pieces in place, it's time to look at the core of
this tutorial, the logic. In order to keep things clear, the different steps of
the logic are implemented as separate flows, some of them could potentially be
combined if you wanted to reduce the number of nodes, that is left as an
exercise for the reader. 

We break the logic down into 5 steps, movement, jump triggering, jump
processing, fall processing and landing.

Firstly, we'll need some variables to use during the logic, add the following
variables to the Player object logic:

 * speed
 * jump_amount
 * fall_amount
 * can_jump

![Variables](../assets/tutorials/simple_platformer_controller/variables.png)


### Movement

This flow is triggered by an "Always" trigger so will run every frame. It
serves two purposes, checking the left right keys and altering the player's
position in the horizontal direction, and applying any jump/fall amounts to
adjust the player's position in the vertical direction. Once this is done, it
will attempt to move the player to the new location.

![Move Logic](../assets/tutorials/simple_platformer_controller/move_logic.png)

Following the flow connections (white) you can see the first thing that happens
after the flow is triggered is to set the "can_jump" variable to 0, this is so
that should the move cause the player to fall off a platform they won't be able
to jump, if the move does not cause the player to start falling, this flag will
be reset by the [Landing](#landing) flow described below.

The next thing in the flow is the actual move, this gets the X and Y position
to move to from a set of calculations. Let's look at X first. 

The "Controller Input" node is configured to return -1 for left and 1 for
right, if either button is not pressed, it will return 0 for that direction.
These two values are added together in a "Math" node, this is to cancel out
should the player press both left and right simultaneously, as 1 + -1 is 0, if
only one button is pressed, the result will be either -1 or 1 depending on
whether left or right is pressed.

The result of this calculation is then fed into another "Math" node that
multiplies the direction by the "speed" variable (don't forget to set the speed
to something other than 0 in the object properties back in the Room editor!).
The result of this calculation is then fed into a third "Math" node that adds
it to the current X position of the player, moving it in the correct direction
by the desired speed.

The Y position is calculated by subtracting the "jump_amount" variable from the
current Y position of the player (remember negative Y is up on the screen), and
then adding in the "fall_amount" variable to account for falling.


### Jump Triggering

Next, in a separate "Always" flow, we check the jump button, note the
"Controller Input" is set to "Just Pressed" for this, as we don't want the jump
to be continuous as we do for the left/right movement, this is one good reason
to keep the flows separate. 

![Jump Logic](../assets/tutorials/simple_platformer_controller/jump_logic.png)

We compare the result from the "Controller Input" to see if jump has just been
pressed. We also check the value of the "can_jump" variable, and feed the
result of both of these comparisons into an "AND" node. Only if the button is
pressed, and the player can jump, do we proceed to make the player jump. This
is done by simply setting the "jump_amount" variable to the initial jump amount
we want, you can tweak this value to get the height you desire for your game.
We also set the "fall_amount" to 0 and the "can_jump" to 0, this prevents the
falling from completely overriding the jump back up in the
[Movement](#movement) flow, and prevents the player from jumping again until
they have landed.


### Jump Processing

Next, in another "Always" flow, we continuously adjust the "jump_amount" if it
is not zero.

![Jump Processing](../assets/tutorials/simple_platformer_controller/jump_logic_2.png)

Here we check if "jump_amount" is greater than zero, which indicates the player
is jumping, if it is, we reduce it by 1 and then clamp the result to make sure
that it doesn't go below zero, if it did, it would add to the falling resulting
in the player falling faster than they should.


### Fall Processing

Next, in yet another "Always" flow, we continuously adjust the "fall_amount" so
that the player falls faster up to a limit, accelerating towards the ground
when they step off a platform.

![Fall Processing](../assets/tutorials/simple_platformer_controller/fall_logic.png)

This simply adds 1 to the "fall_amount" each frame and then clamps it to a
reasonable range so the player doesn't fall too fast, you can tweak the upper
limit of the clamp to get the desired maximum falling speed for your game.


### Landing

Finally for now, we have the logic flow that reacts when the player has
collided with something. The "Collided" trigger is automatically run when the
"Move Object" node in the [Movement](#movement) flow results in the player
hitting something. For the purposes of this tutorial, we know it can only be a
platform or the ground, but we check the direction for completeness anyway and
to ensure that collision in other directions is cleanly handled as you continue
to develop your game around this controller.

![Landing](../assets/tutorials/simple_platformer_controller/land_logic.png)

The flow first checks if the sides includes "TOP" which is 2, it does this by
logically ANDing the sides value with 2. Recall that the sides is a bit field,
bit 0 (value 1 if collided) is UP, i.e. the move resulting in the object
hitting something from below, bit 1 (value 2 if collided) is DOWN, bit 2 (value
4 if collided) is LEFT and bit 3 (value 8 if collided) is RIGHT. The actual
valud of sides is a potential combination of these values, for example, if the
object collided in both the DOWN and LEFT directions, the value will be 2 + 4 =
6, ANDing with 2, will remove any other directions from the value but the DOWN
value, so if the player does collide both DOWN and LEFT, LEFT will be ignored,
the output from 6 AND 2 is 2, as illustrated by the binary representation below. 

                RLDU
    6       00000110
    2       00000010

Only if both "bits" in the binary number are 1, will the bit be 1 in the
result, so the result of ANDing these two number will be 00000010 in binary,
which is 2. This means we can just compare the result with 2 to check if the
object collided in a downwards direction at all, irrespective of whether it
collided in another direction as well or not.

If this is true, we set the "fall_amount" variable to 0, the [Fall
Processing](#fall_processing) flow will increase it to take care of falling off
a platform next time round, and set the "can_jump" variable to 1 to indicate
that the player can now jump again as they have landed.


## Testing

That should be all that is required to get a basic platformer control working
in Kwyll. Switch to the Preview tab and start the game, you should be able to
move left and right, and jump up onto the platforms. When you walk off a
platform the player should fall to the ground.


![Preview](../assets/tutorials/simple_platformer_controller/preview.png)
