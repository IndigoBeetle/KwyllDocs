
# Get


## Description

![Get Node](../../assets/nodes/get_node.png){align=left} The *Get Node* is used
to get the integer value of a variable on whatever the current logic graph is
running, i.e. a [Screen](../../introduction/terminology.md#screens), a
[Room](../../introduction/terminology.md#rooms) or an
[Object](../../introduction/terminology.md#objects).

It's important to understand that the value being returned is the value for the
chosen variable in the [Object
Reference](../../introduction/terminology.md#objects) that is running the logic
code, each reference has it's own version of the variables, so accessing a
variable on one reference for a particular object type will not necessarily
return the same value as for another reference, they are independent.

<br style="clear:left"/>
  
-------

## Ports

*Output* 
: An integer output port that will provide the value of the chosen variable.


-------

## Parameters

Variable 
: A dropdown listing the defined variables associated with the current logic graph.

