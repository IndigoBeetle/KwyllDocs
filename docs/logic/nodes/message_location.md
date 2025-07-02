
# Message Location 

## Description

![Message Location Node](../../assets/nodes/message_location.png){align=left width="25%"}
The *Message Location Node* sends a message to a specified location. 
The room logic for the location should have an [On Message](./on_message.md) node 
correctly configured to handle the message, otherwise it will have no effect.

The ID of the message is used to choose which [On Message](./on_message.md)
flow will handle the message, and the optional parameters P1 and P2 are passed
to the message handler to provide additional information that can be arbitrarily
defined by the game designer.

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

Location 
: A location reference port that provides a reference to the location that the
  message will be sent to. If not connected, and the logic is on a location, 
  the current location will be used.

ID 
: An integer input port used to provide ID of the message, this controls which
  flow on the global object will handle the message, only [On Message](./on_message.md)
  flows with a matchin ID will be executed.

P1 
: An integer input port used to provide an arbitrary parameter to the handler, the
  purpose of which is defined by the game designer.

P2 
: An integer input port used to provide an arbitrary parameter to the handler, the
  purpose of which is defined by the game designer.

-------

## Parameters

ID 
: A constant integer value for the message ID, used when the __ID__ port is not
  connected.

P1 
: A constant integer value for the optional P1 parameter, used when the __P1__ 
  port is not connected.

P2 
: A constant integer value for the optional P2 parameter, used when the __P2__ 
  port is not connected.


