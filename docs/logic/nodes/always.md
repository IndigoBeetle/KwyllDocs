# Always

## Description

![Always Node](../../assets/nodes/always.png){align=left width="25%"}
The *Always Node* is a specific type of *Node* called a __Trigger__. A trigger
*Node* is an entrypoint into a flow in the Kwyll logic. The *Always* trigger is
the most commonly used trigger node, it will run the flow that follows on from
it's __Flow Out__ port every update of the game unless the *Skip* parameter is
set to a non-zero positive value, in which case it will skip that many updates
before running the flow, and then start again.

<br style="clear:left"/>

-------

## Ports

Flow Out
: As with all trigger nodes, an *Always Node* has only a single flow port
  on the output side. There is no input flow to a trigger node as it is
  the origin of a flow.


-------

## Parameters

Order 
: This is used to define the order in which multiple *Always Nodes* in a single
  logic program will be processed, in case there is some dependency between
  flows. If there are multiple *Always Nodes* with the same order, they will be
  processed together in an arbitrary order.

Skip 
: This parameter is used to delay the execution of the flow for a specified 
  number of frames. If it is zero, the flow will run on every update as normal,
  any non-zero positive number will skip that many updates before running the
  flow.
