# Always

![Always Node](../../assets/nodes/always_node.png){align=left} The *Always
Node* is a specific type of *Node* called a __Trigger__. A trigger
*Node* is an entrypoint into a flow in the Kwyll logic. Only if a logic
program on an object or anything else has trigger nodes will the logic
do anything. The *Always* trigger is the most common of trigger node, it
will run the flow that follows on from it's flow output on every frame
of the game.

## Ports

### Flow Out

As with all trigger nodes, an *Always Node* has only a single flow port
on the output side. There is no input flow to a trigger node as it is
the origin of a flow.

## Parameters

### Order 

*Always Nodes* have a single additional parameter, __order__. This is
used to define the order in which multiple *Always Nodes* in a single
logic program will be processed, in case there is some dependency
between flows. If there are multiple *Always Nodes* with the same order,
they will be processed together in an arbitrary order.
