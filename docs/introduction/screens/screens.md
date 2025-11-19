
# Screens

A *Screen* in Kwyll is a collection of
[Instruments](../terminology.md#instruments), a
[Tilemap](../terminology.md#tilemap), and optionally, the game window. A
*Screen* can also have [logic](../terminology.md#logic) associated with it that
is run while it is the current screen. 

A *Screen* can optionally be defined as a "game screen", which means it will
display the game window, the game window can be placed arbitrarily within the 
*Screen*, and different screens can have the game window in a different place,
the game window size however, is fixed for all screens.

There is only one *Screen* active at any time in a Kwyll game. Uses of screens
include the a menu screen, instructions, and the main game screen which will 
have the game window positioned on the screen accordingly.

