
# Select

## Description

![Select Node](../../assets/nodes/select.png){align=left width="25%"}
The *Select Node* takes an index value and returns the corrent entry from
a fixed list of integer values added to the node. Values are added using the 
plus button, and can be reordered and removed using the buttons next to each
list entry.

The __Mode__ parameter defines what the node will do if the provided index 
is out of range for the number of items in the list. If it is set to __Wrap__
any index greater than or equal to the number of items, as the index is zero
based, will roll back round to the start again, so in a list with 3 items, if the 
index provided was 4, the list entry at index 1 (the second in the list) will 
be returned. Similarly, values less than 0 will roll round to the end of the list.
If the __Mode__ is __Clamp__, out of range values will be limited to 0 and 
the number of items minus 1.

<br style="clear:left"/>
  
-------

## Ports

Index 
: An integer input port used to provide the index into the list.

*Out*
: An integer output port that provides the value of the chose list item.

-------

## Parameters

Index 
: A constant integer value for the index, used when the __Index__ port is not
  connected.

Mode 
: The method to use to deal with out of range indices, __Wrap__ or __Clamp__.


