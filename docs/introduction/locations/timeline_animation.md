
# Timeline Animation

![Timeline](../../assets/timeline.png)

When *Object Types* are added to a *Room Type* as an *Object Instance*, it is
possible to animate the position of those instances in the room without using
logic for simple animation requirements, such as following a path. In the [Room
Editor](../../interface/room_editor.md) there is an animation timeline editor
which represents time in frames. With this editor you can place "keyframes" at
any point in time (up to 65535) which hold a position for the object being
animated. At runtime, the Kwyll engine will interpolate between those keyframes
over time. So you can place a keyframe at time 0 and one at time 50, and the
position will change between the position stored on the first and the position
stored on the second over 50 frames.

Timeline animation also provides another useful feature, it is possible to
trigger [logic](../terminology.md#logic) at any point in the timeline, so you
can have an animation that moves an object along a path, and at certain points
in that path triggers logic on the object to perform a particular action, such
as changing the sprite animation, or firing a projectile.

