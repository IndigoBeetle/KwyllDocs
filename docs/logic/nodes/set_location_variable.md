
# Set Location Variable

## Description

![Set Location Variable Node](../../assets/nodes/set_location_variable.png){align=left width="25%"}
The *Set Location Variable Node* is used to set the integer value of a variable on
a given [Location](../../introduction/terminology.md#locations).


<br style="clear:left"/>
  
-------

## Ports

Flow In
: In order for this node to perform its operation, it must be connected into an
  active flow using this input port. The flow will ultimately originate at a
  __Trigger__ node but can come from the __Flow Out__ port of any other flow
  node.

Valid
: A node connected to the __Valid__ port will be executed in sequence if the
  specified location is using the correct Room Definition.

Invalid
: A node connected to the __Invalid__ port will be executed in sequence if the
  specified location is not using the correct Room Definition.

Location 
: A location reference port that provides a reference to the location that contains
  the variable to be modified. If not connected, and the logic is on
  a location, the current location will be used.

Value 
: An integer input port that provides the value to be assigned to the chosen variable.


-------

## Parameters

*Variable*
: A dropdown listing the defined variables associated with the specified location.

*Room Definition*
: A dropdown listing the available room definitions. Only if the specified location
  uses the room definition chosen will the variable be modified and the valid flow
  be followed.


