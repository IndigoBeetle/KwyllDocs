
# Set Global Variable

## Description

![Set Global Variable Node](../../assets/nodes/set_global_variable.png){align=left width="25%"}
The *Set Global Variable Node* is used to set the integer value of a variable on
the Global [Logic](../../introduction/terminology.md#logic).


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

Value 
: An integer input port used to provide the value that will be applied to the
  chosen variable.


-------

## Parameters

Value
: A constant integer value to assign to the chosen variable. If the port is 
  connected to another node, this option will become unavailable, the node
  will use the value provided on the input port.

*Variable*
: A dropdown listing the defined variable names on the global logic graph.

