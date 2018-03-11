# Generating Random Numbers

### Table of Contents

[1. Introduction](#introduction)  
[2. True Random Number Generators](#true-random-number-generators)  
[3. Pseudo-random Number Generators](#pseudo-random-number-generators)
* [3.1. Middle-square method](#middle-square-method)  

[4. Difference between PRNG and TRNG](#difference-between-prng-and-trng)  
[5. Sources](#sources)

## Introduction

It is difficult to get a computer to do something by chance. A computer follows its instructions blindly and is therefore **completely predictable**. There are two main approaches to generating random numbers using a computer: **Pseudo-Random Number Generators (PRNGs) and True Random Number Generators (TRNGs)**.

## True Random Number Generators

TRNGs extract randomness from **physical phenomena** and **introduce it into a computer**.  A really good physical phenomenon to use is a radioactive source. The points in time at which a radioactive source decays are completely unpredictable, and they can quite easily be detected and fed into a computer, avoiding any buffering mechanisms in the operating system. **The drawback is that it is way slower than a PRNG**.

## Pseudo-random Number Generators

PRNG use **algorithms that use mathematical formulae or simply precalculated tables** to produce sequences of numbers that appear random. The PRNG-generated sequence is not truly random, because it is completely determined by an **initial value, called the PRNG's seed** (which may include truly random values). 

### Middle-square method

The middle-square method is a **method of generating pseudorandom numbers**. In practice it is not a good method, since its **period is usually very short**. It was invented by John von Neumann.

![Middle-square](https://upload.wikimedia.org/wikipedia/commons/thumb/9/92/Middle-square_method.svg/250px-Middle-square_method.svg.png)

* Select a seed number, which will be the input. 
* Multiply the seed by itself and take the middle of the result
* Repeat with the middle being the new seed as many time as you want

**Example:**

```
Seed: 121
First result: 14641
Middle part: 464
Next result: 215296
Middle part: 529
...
```

## Difference between PRNG and TRNG

The best way to see the difference between the two is to generate their **random walk**, which is  mathematical object that describes a path that consists of a succession of random steps on some mathematical space such as the integers.

![Random Walk example](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/Random_walk_25000_not_animated.svg/280px-Random_walk_25000_not_animated.svg.png)

The random walk will seem similar at first until we reach the point where the PRNG repeats itself (by reusing a seed it has used before), while the TRNG will continue randomly. This depends on the **period** of the PRNG. The larger it is, the better.

## Sources

* [https://www.khanacademy.org/computing/computer-science/cryptography/crypt/v/random-vs-pseudorandom-number-generators](https://www.khanacademy.org/computing/computer-science/cryptography/crypt/v/random-vs-pseudorandom-number-generators)
* [https://en.wikipedia.org/wiki/Middle-square_method](https://en.wikipedia.org/wiki/Middle-square_method)
* [https://www.random.org/randomness/](https://www.random.org/randomness/)
