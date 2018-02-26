# Arrays

### Table of Contents

[1. Definition](#definition)  
[2. Find an element](#find)  
[2. Add an element](#add)  
[3. Dynamic Arrays](#dynamic)  
[4. Time complexity](#time)  
[5. Sources](#sources)

<a name="defintion"></a>

## Definition

An array is a **contiguous area of memory** consisting of **equal-size elements** **indexed by contiguous integers**. 

<a name="find"></a>

## Find an element

These indexes allow us to have **a constant-time access**, as we can use simple arithmetics to find an element:

``` arr_addr + elem_size * i ``` (if zero-based indexing, which is usually the case)

For multi-dimensional arrays, we just have to skip the rows until we reach the one we are interested in. For a two-dimensional array, that would give:
 
``` arr_addr + elem_size * (col_number + row_number * nb_elements_in_a_row) ``` (if zero-based indexing)

<a name="add"></a>

## Add an element

### At the end of the array

If we add an element at the end of the array, it is quite simple since we juste have to get the next index and put the new value there. This action would **cost O(1)** in terms of time complexity. 

#### Example

Index | 0 | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- | --- |
Value | 0 | 10 | 20 | 30 | 40 | 50 |

Adding 60 at index 6 is straight-forward:

Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| --- | --- | --- | --- | --- | --- | --- | --- |
Value | 0 | 10 | 20 | 30 | 40 | 50 | 60

### Anywhere else

But if we want to add the element somewhere else, it is trickier. Not only do we have to change the value at one of the index, but we also have to reorganize all of the other elements, which would **cost O(n)** in terms of time complexity.

#### Example

Index | 0 | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- | --- |
Value | 0 | 10 | 20 | 30 | 40 | 50 |

Now, let's add 60 at index 2:

Step 1: Move all of the elements above the index 2 on the right

Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| --- | --- | --- | --- | --- | --- | --- | --- |
Value | 0 | 10 |  | 20 | 30 | 40 | 50 |

Step 2: Change the value at index 2: 

Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| --- | --- | --- | --- | --- | --- | --- | --- |
Value | 0 | 10 | 60 | 20 | 30 | 40 | 50 |

<a name="dynamic"></a>

## Dynamic Arrays

In fixed-size arrays, one **cannot add more elements than the capacity chosen for this array when it was created**. But dynamic arrays allow that: **we can add as many elements as we want**. In some languages, arrays are directly resizable and in others, you would have to use a different class, like ArrayList in Java.

The way it works is, whenever the capacity of the array is not enough to store the element the user wants to add, it is simply **doubled**. Which also means we waste some space here.

<a name="time"></a>

## Time complexity

Indexing | Insert / Delete at the beginning | Insert / Delete at the end | Insert / Delete in middle | 
--- | --- | --- | --- | 
O(1) | O(n) | O(1) | O(n) |

<a name="sources"></a>

## Sources

* [https://www.coursera.org/learn/data-structures/lecture/OsBSF/arrays](https://www.coursera.org/learn/data-structures/lecture/OsBSF/arrays)
* [https://www.lynda.com/Software-Development-tutorials/Resizable-arrays/149042/177108-4.html](https://www.lynda.com/Software-Development-tutorials/Resizable-arrays/149042/177108-4.html)
* [https://en.wikipedia.org/wiki/Array_data_structure#Efficiency](https://en.wikipedia.org/wiki/Array_data_structure#Efficiency)
* [https://en.wikipedia.org/wiki/Dynamic_array](https://en.wikipedia.org/wiki/Dynamic_array)
