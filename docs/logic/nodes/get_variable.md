
# Get Variable


## Description

![Get Variable Node](../../assets/nodes/get_node.png){align=left} The *Get
Variable Node* is used to get the integer value of a variable on whatever the
current logic graph is running, i.e. a
[Screen](../../introduction/terminology.md#screens), a
[Room](../../introduction/terminology.md#rooms) or an
[Object](../../introduction/terminology.md#objects).

It's important to understand that, in the case of
[rooms](../../introduction/terminology.md#rooms) and
[objects](../../introduction/terminology.md#objects) the value being accessed
is the value for the chosen variable in the [Object
Reference](../../introduction/terminology.md#objects) or
[Location](../../introduction/terminology.md#locations), that is running the logic
code, each reference has it's own copy of the variables, they are independent.


<br style="clear:left"/>
  
-------

## Ports

*Output* 
: An integer output port that will provide the value of the chosen variable.


-------

## Parameters

*Variable*
: A dropdown listing the defined variables associated with the current logic graph.

