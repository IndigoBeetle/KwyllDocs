
# Set Instrument

## Description

![Set Instrument Node](../../assets/nodes/set_instrument_value.png){align=left width="25%"}
The *Set Instrument Node* takes input values X and Y that specify a position 
on the map and will change to the [Location](../../introduction/terminology.md#locations)
at that point on the map if there is one. If there is no location at the specified
coordinates, nothing happens.

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

Instrument 
: An integer input port used to provide the index of the instrument on the screen.

Value
: An integer input port used to provide the value to apply to the instrument.

-------

## Parameters

Instrument 
: A constant integer value for the instrument index, used when the __Instrument__ 
  port is not connected.

Value
: A constant integer value for the value, used when the __Value__ port is not connected.


