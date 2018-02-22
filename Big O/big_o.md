# Big O

### Table of contents

[1. Introduction](#introduction)  
[2. Math](#math)  
[3. Common Big Os](#bigo)  
[4. Best, average and worst case](#worst)  
[5. Some common algorithms' Big O](#algorithms)  
[6. Sources](#sources)  


<a name="introduction"></a>

## Introduction

One of the most important question when creating an algorithm is: How fast is it? Since using a time measurement would not make any sense as a more recent computer would be faster than an old one and that many factors can influence the results, we need to find a way that tells us the efficiency of the algorithm regardless of the hardware we are using... This is why the **Big O notation** is used, which, in a nutshell, will tell us **how the runtime grows as the size of the input grows as well**. Of course, the smaller, the better...

This notation is also used for the space requirements of the algorithm.

<a name="math"></a>

## Math

### Definition

Let f and g be two functions defined on some subset of the real numbers. f(x) = O(g(x)) if and only if there is a positive real number M and a real number x0, such that:

| f(x) | <= M | g(x) | for all x >= x0

### Properties

##### Product

* f1 = O(g1) and f2 = O(g2) ⇒ f1 f2 = O(g1 g2)
* f O(g1) ⇒ O(f g1)

#### Sum

* f1 = O(g1) and f2 = O(g2) ⇒ f1 + f2 = O(| g1 | + | g2 |)

#### Multiplication by a constant

* f1 = O(g1) ⇒ k f1 = O(g1) with k being a constant

<a name="bigo"></a>

## Common Big Os

Here are the most common big O's one will find in Computer Science, sorted in terms of their speed.

Big O | Name |
--- | --- |
O(1) | Constant |
O(log(n)) | Logarithmic |
O(n) | Linear |
O(n log(n)) | Log Linear |
O(n²) | Quadratic |
O(n³) | Cubic |
O(2^n) | Exponential |

![Comparing the Big O's](http://interactivepython.org/runestone/static/pythonds/_images/newplot.png)




#### O(1)

An algorithm that will always execute in the same time (or space). 

```python
def is_first_element_null(array)
  if array[0] == nil
    return true
  else
    return false
  end
end
```
#### O(log(n))

If you double the problem size n, your algorithm needs only a constant number of steps more. This is reached by algorithms who will cut down the problem in half each time, like the binary search:

```python
def binary_search(array, value, low=0, high=array.size-1)
  # if high and low overlap, nothing was found.
  return false if high < low
  # Determine the middle element.
  mid = low + ((high - low) / 2)
  # Split the result in half and search again recursively until we succeed.
  if array[mid] > value
    return binary_search(array, value, low, mid-1)
  elsif array[mid] < value
    return binary_search(array, value, mid+1, high)
  else
    return mid # Found!
  end
end
```
 
#### O(n)

Such an algorithm will grow linearly: for every element, you perform a constant number of operations. Most of the time, this is reached by going through all of the elements of the data with a for loop.

```python
def contains_value(array, value)
  for entry in array
    return true if entry == value
  end
  return false
end
```

#### O(n²)

This is where things are starting to get bad and where algorithms will not scale very well. Most of the time achieved with multiple nested iterations over the data set. The more nested loops, the higher the exposant...

```python
def contains_duplicates(array)
    i = 0
    while i < array.size
        j = i + 1
        while j < array.size
            return true if array[i] == array[j] # Found a match!
            j += 1
        end
        i += 1
    end
    return false
end

```

#### O(2^n)

These algorithms' runtime (or space usage) will double for each element added to the data set. Such algorithms become inefficiant really fast.

```python
def fibonacci(int number)
{
    if (number <= 1): return number;

    return fibonacci(number - 2) + fibonacci(number - 1);
}
```

<a name="worst"></a>

## Best, average and worst case

Big O's are calculated using the worst case scenario. But one can also consider the best and average one. For example, if you look for the first element in a list, it will take much less time than looking for the last one, since you would have to go through the whole data set in this case... 

It some cases, an algorithm with a higher order for the worst case can be, in average, way better than one with a smaller order. This is true for some sorting algorithms like **quicksort**. 

<a name="algorithms"></a>

## Some common algorithms' Big O

Here is a website listing the big O for common algorithms:

[http://bigocheatsheet.com/](http://bigocheatsheet.com/)

<a name="sources"></a>

## Sources

* [https://www.daveperrett.com/articles/2010/12/07/comp-sci-101-big-o-notation/](https://www.daveperrett.com/articles/2010/12/07/comp-sci-101-big-o-notation/)
* [http://interactivepython.org/runestone/static/pythonds/AlgorithmAnalysis/BigONotation.html](http://interactivepython.org/runestone/static/pythonds/AlgorithmAnalysis/BigONotation.html)
* [https://en.wikipedia.org/wiki/Big_O_notation](https://en.wikipedia.org/wiki/Big_O_notation)
* [https://www.youtube.com/watch?v=iOq5kSKqeR4](https://www.youtube.com/watch?v=iOq5kSKqeR4)
