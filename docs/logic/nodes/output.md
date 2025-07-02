
# Output

## Description

![Output Node](../../assets/nodes/output.png){align=left width="25%"}
The *Output Node* represents an output value from a 
[Sub Graph](../../concepts/logic.md#subgraphs). The provided name is used on the 
sub graph node as the name for the output port.

It is entirely normal to use the same name on multiple output ports, only one will
provide the output value to the port on exiting the sub graph, the last one 
encountered in the flow. This allows you to set the output to different values
depending on the flow throught the sub graph.

See [Sub Graphs](../../concepts/logic.md#subgraphs) for more information regarding
the use of sub graphs.

<br style="clear:left"/>
  
-------

## Ports

*In*
: An input port, the value passed into this port will be provided up to the sub
  graph node on exit.


-------

## Parameters

Name 
: The name of the port on the sub graph that will represent this output value.




