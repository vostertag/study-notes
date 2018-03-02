# Hash Table

### Table of Contents

[1. Hashing](#hash)  
[2. Hash Functions](#functions)  
[3. Hash Table](#table)  
[4. Time Complexity](#time-complexity)  
[5. Sources](#sources)

<a name="hash"></a>

## Hashing

Hashing is a technique that is used to **uniquely identify a specific object from a group of similar objects**. For example, a student has a unique number to represent him inside a university.

* Hashing must be deterministic under the same context
* If two objects return the same hash, they are equal
* **Hash collisions**: the same hash may result from different objects

<a name="functions"></a>

## Hash functions

To do so, one must use what is called a **hash function**, which will take data and return a reference for it, that will be way smaller in size. These functions are usually **not invertible** (it is impossible to get the data thanks to its reference) and **some informations about the data will be lost**.

The hash can then be used as an index (after it has been reduced) to store the data in what is called a **hash table** or a **dictionary**.

A *good* hash function should:

* Be easy to compute
* Have a uniform distribution (to avoid clustering)
* Have Less collisions

**Note:** Irrespective of how good a hash function is, **collisions are bound to occur**. Therefore, to maintain the performance of a hash table, it is **important to manage collisions** through various collision resolution techniques.

<a name="table"></a>

## Hash Table

### Definition

A hash table (hash map) is a data structure which **implements an associative array abstract data type, a structure that can map keys to values**.

### Adding an element

A hash table is simply a very large array with some added features. Each available slot for a new value is called a **bucket**. When adding a pair of key and value to the table, it will **use its hash function to generate a hash value**, which can be quite large. Therefore, that value **must be reduced** in consideration of the size of the hash table in order to use it as an index for the value (for example by using modulos). Once reduced, we add to the corresponding bucket, the new value.

### Finding an element

To get an element from the hash table, one must **provide a key**. This key will be **associated to a hash value** by the hash function and then **reduced** in some ways. Thanks to this, we will **get the index of the value** we are looking for...

### Managing collision

As said earlier, it can happen that **two different objects have the same hash**, this is a **collision**. In order to manage it, the hash table have different options.

#### Separate chaining

Each bucket is independent, and **has some sort of list of entries with the same index, like an array or a linked-list**.

![Seperate chaining](https://he-s3.s3.amazonaws.com/media/uploads/0e2c706.png)

#### Open addressing

In open addressing, if a bucket at the hashed index is unoccupied, then the entry record is inserted in slot at the hashed index else **it proceeds in some probe sequence until it finds an unoccupied slot**. The **probe sequence** is the sequence that is followed while traversing through entries. In different probe sequences, you can have different intervals between successive entry slots or probes.

## Time Complexity

Algorithm |	Average | Worst case |
--- | --- | --- |
Space |		O(n) |	O(n) |
Search 	|	O(1) |	O(n) |
Insert 	|	O(1) | O(n) |
Delete 	|	O(1) | O(n) |

## Sources

* [https://www.lynda.com/Software-Development-tutorials/Using-hash-tables/149042/177127-4.html](https://www.lynda.com/Software-Development-tutorials/Using-hash-tables/149042/177127-4.html)
* [https://en.wikipedia.org/wiki/Hash_table](https://en.wikipedia.org/wiki/Hash_table)
* [https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)
