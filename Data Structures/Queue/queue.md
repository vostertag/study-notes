# Queue

### Table of Contents

[1. Definition](#definition)  
[2. Implementation](#implementation)  
[3. Basic Operations](#operations)  
[4. Sources](#sources)

<a name="definition"></a>

### Definition

A queue is a collection in which the entities are **kept in order** and the principle (or only) operations on the collection are the **addition of entities to the rear** terminal position, known as **enqueue**, and **removal of entities from the front** terminal position, known as **dequeue** (**FIFO**: First In, First Out).

![Queue](https://upload.wikimedia.org/wikipedia/commons/thumb/5/52/Data_Queue.svg/405px-Data_Queue.svg.png)

<a name="implementation"></a>

### Implementation

Queues can easily be implemented with a linked-list that has a pointer to its head, and to its tail, or with an array.

<a name="operations"></a>

### Basic Operations

```enqueue()```: add to the queue  
```dequeue()```: remove from the queue  
```empty()```: check if the queue is empty

All of these operations are **O(1)**.

<a name="sources"></a>

### Sources

* [https://www.coursera.org/learn/data-structures/lecture/EShpq/queue](https://www.coursera.org/learn/data-structures/lecture/EShpq/queue)
* [https://en.wikipedia.org/wiki/Queue_(abstract_data_type)](https://en.wikipedia.org/wiki/Queue_(abstract_data_type))
