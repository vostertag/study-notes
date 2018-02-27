# Linked List

### Table of Contents

[1. Defintion](#definition)  
[2. Types of list](#types)  
[3. Find an element](#find)  
[4. Add an element](#add)  
[5. Time complexity](#time)  
[6. Sources](#sources)

<a name="definition"></a>

## Definition

A linked list is a **linear collection of data elements**, where each element **points to the next one**.

![Linked list](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Singly-linked-list.svg/408px-Singly-linked-list.svg.png)

<a name="types"></a>

## Types of linked list

There are different types of linked list. The most common being the **singly linked list** introduced in the definition.

### Doubly linked list

Same as a singly linked list, but we also have a pointer to the previous element.

![Doubly linked list](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Doubly-linked-list.svg/610px-Doubly-linked-list.svg.png)

### Circular linked list

Similar to a singly linked list, but the last elements points to the first one.

![Circular linked list](https://upload.wikimedia.org/wikipedia/commons/thumb/d/df/Circularly-linked-list.svg/350px-Circularly-linked-list.svg.png)

<a name="find"></a>

## Find an element

To find an element in a linked-list, one has to go through all of the nodes until he finds the one he is interested in. Therefore, it has a **O(n) time complexity**.

<a name="add"></a>

## Add an element

### At the front of the list

Adding an element in front of a linked-list has a time complexity of **O(1)**. The steps to follow are:

1. Create a node containing the new value and pointing to the previous first node of the list
2. Update the head pointer of the linked list to point to this new node

### At the end of the list

Adding an element at the end of a linked-list has a time complexity of **O(n)** since we need to go through the list:

1. Go through each node until the final one is found
2. Create a new node with the new value
3. Update the pointer of our previous final node to this new node

**Note:** To go faster, it is possible to add a tail pointer which points to the end of the linked-list. In which case, this would be of O(1) in terms of time complexity. BUT removing the last element, even with this tail pointer, would still be O(n) since we would not be able to find the node previous to the last one...

<a name="time"></a>

## Time complexity

Indexing | Insert / Delete at the beginning | Insert / Delete at the end | Insert / Delete in middle | 
--- | --- | --- | --- | 
O(n) | O(1) | O(1) / O(n) if end node is known | O(n) |

<a name="sources"></a>

## Sources

* [https://en.wikipedia.org/wiki/Linked_list](https://en.wikipedia.org/wiki/Linked_list)
* [https://www.coursera.org/learn/data-structures/lecture/kHhgK/singly-linked-lists](https://www.coursera.org/learn/data-structures/lecture/kHhgK/singly-linked-lists)





