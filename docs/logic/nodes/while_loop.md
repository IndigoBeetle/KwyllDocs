
# While Loop 

## Description

![While Loop Node](../../assets/nodes/while_loop.png){align=left width="25%"}
 The *While Loop Node* will run the node flow that is connected to its *Body* output port
 repeatedly while the result of evaluating the input at the __Condition__ port is non-zero.

 When the loop is complete, the logic graph will continue with the flow connected to the
 *Exit* port.

<br style="clear:left"/>
  
-------

## Ports

Flow In
: In order for this node to perform its operation, it must be connected into an
  active flow using this input port. The flow will ultimately originate at a
  __Trigger__ node but can come from the __Flow Out__ port of any other flow
  node.

Body
: The nodes that are to be repeatedly executed during the loop. Execution will 
  continue while there is a node connected to the Flow Out of the last node
  executed, the body ends when there is no connection to the Flow Out, at which
  point the index is updated and the node will check if it is to run the loop 
  again or exit.

Condition
: An integer input port providing the value to check at each loop iteration.
  If the value is 0, the loop exits, if it is non-zero, it loops again.

Exit
: A node connected to the __Flow Out__ port will be executed in sequence
  following the completion of this node's operation.


