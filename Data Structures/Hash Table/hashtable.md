# Hash Table

### Table of Contents

[1. Hashing](#hash)  
[2. Hash Functions](#functions)

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

* Easy to compute
* Have a uniform distribution (to avoid clustering)
* Less collisions

**Note:** Irrespective of how good a hash function is, **collisions are bound to occur**. Therefore, to maintain the performance of a hash table, it is **important to manage collisions** through various collision resolution techniques.

##
