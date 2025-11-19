
# Object Types

In order to use objects in your Kwyll game, you must first describe to Kwyll
what your objects are and how they work, this is done by creating "Object Types".

The type of an object details things including what it looks like, via
[Sprites](../terminology.md#sprites) and any other information that is
required to display the object that may be platform specific, such as colour
and draw mode, and any [Logic](../terminology.md#logic). 

An *Object Type* consists of two main elements.

 - Animations, which are sequences of [Sprite](../terminology.md#sprites)
   images played in order to create the illusion of animation. Each object can
   have many Animations, for example, a player object might have an animation
   for walking left, one for walking right, one for jumping, one for attacking
   etc. The game designer can choose which Animation is played using the logic
   nodes based on what is happening in the game at that moment.
 - [Logic](../terminology.md#logic) is the "brains" of an Object, it defines
   what an Object does, and when. In Kwyll, logic is created using a visual
   programming tool, a powerful means of writing code without writing code.
