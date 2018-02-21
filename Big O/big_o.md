# Big O

### Table of contents

[1. Introduction](#introduction)  
[2. Math](#math)  

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

## Algorithms
