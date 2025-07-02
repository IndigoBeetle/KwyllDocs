
# Sub Graph


## Description

![Sub Graph Node](../../assets/nodes/sub_graph.png){align=left width="25%"}
The *Subgraph Node* is a dynamic node that represents a separate graph contained
within it. The input and output ports on the *Sub Graph Node* will depend on the
contents of the contained graph, specifically the use of [Input](./input.md) and
[Output](./output.md) nodes. 

The node has an additional button not present on any other nodes, the down arrow
on the top right of the node. Selecting this will open the graph contained within
the sub graph for editing.

See [Sub Graphs](../../concepts/logic.md#subgraphs) for more information regarding
the use of sub graphs.

<br style="clear:left"/>
  
-------

## Ports

Flow In
: In order for this node to perform its operation, it must be connected into an
  active flow using this input port. The flow will ultimately originate at a
  __Trigger__ node but can come from the __Flow Out__ port of any other flow
  node.

Flow Out
: A node connected to the __Flow Out__ port will be executed in sequence
  following the completion of this node's operation.

