# Stack

### Table of Contents

[1. Definition](#definition)  
[2. Basic Operations](#operations)  
[2. Sources](#sources)  

<a name="definition"></a>

## Definition

A stack is a structure where **insertion and deletion of items takes place at one end** called top of the stack. It is named stack as it behaves like a real-world stack...

![Stack representation](https://www.tutorialspoint.com/data_structures_algorithms/images/stack_representation.jpg)

<a name="operations"></a>

## Basic Operations

```push(NewItem item)```: adds an item onto the stack  
```top()```: Returns the last item ppushed onto the stack  
```pop()```: Removes the most-recently pushed item from the stack  
```is-empty()```: True if no more items can be popped and there is no top item  
```get-size()```: Returns the number of elements on the stack 

All operations except get-size() can be performed in O (1). get-size() runs in at worst O (n).

<a name="sources"></a>

## Sources

* [https://www.tutorialspoint.com/data_structures_algorithms/stack_algorithm.htm](https://www.tutorialspoint.com/data_structures_algorithms/stack_algorithm.htm)
* [https://en.wikibooks.org/wiki/Data_Structures/Stacks_and_Queues](https://en.wikibooks.org/wiki/Data_Structures/Stacks_and_Queues)
* [https://www.coursera.org/learn/data-structures/lecture/UdKzQ/stacks](https://www.coursera.org/learn/data-structures/lecture/UdKzQ/stacks)
