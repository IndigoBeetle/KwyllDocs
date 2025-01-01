# And

## Description

![And Node](../../assets/nodes/and_node.png){align=left} The *And Node* takes
two inputs of type integer and compares them with 0. If both are not 0, the
output will be 1, if either or both are 0, the output will be 0. 

This is useful to combine checks, in particular with the [Integer
Compare](integer_compare.md) nodes.


<br style="clear:left"/>


-------

## Ports

A and B
: The two input values, they must be linked for the node to be operational and
  can only be connected to sources that provide an integer value, such as
  [Get](get_variable.md).

Out  
: The output of the node, will be either 1 or 0 depending on the result of
  the compare.


