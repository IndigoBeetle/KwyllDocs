
# Store Value 

## Description

![Store Value Node](../../assets/nodes/store_value.png){align=left width="25%"}
The *Store Value Node* takes a single input value and stores it for future use.
When the __Out__ value is requested, it returns the value that it stored, without
running any nodes that connect to the __In__ port as would normally happen.

This node is very useful to optimise the execution of logic. Under normal conditions,
whenever a node requests the value on any of its input ports, the logic will
be executed on the node that connects to that port, and any nodes that connect
to that node, and so on. This can be expensive if the value is used multiple times, 
especially if it doesn't change. So putting a *Store Value Node* in place ensures that
the calculation only happens once, and the resulting value is reused.

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

In 
: An integer input port used to provide the value to store for future use.
  This port will only request its value once, no matter how many times the 
  __Out__ port is used.

Out 
: An integer output port that provides the stored value.


