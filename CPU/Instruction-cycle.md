# CPU's Instruction Cycle

### Table of contents  
[1. Introduction](#introduction)  
[2. Components and buses](#components)  
[3. Steps of the cycle](#steps)  
[4. Sources](#sources)


<a name="introduction"/>

## Introduction

The **FETCH - DECODE - EXECUTE cycle** is the basic operational process of a computer.

This is how a computer :

* Retrieves instructions from the memory
* Determines the actions it should take
* Execute them

**The CPU does that from boot-up to when the computer is shut-down.**

<a name="components"/>

## Components and Buses



### Components

* The *Program Counter (PC)*: It holds the adress of the next instruction
* The *Memory Address Register (MAR)*: It holds the address of the memory to read or to write to
* The *Memory Data Register (MDR) / Memory Buffer Register (MBR)*: It holds the data fetched of the memory or the data waiting to be stored in the memory
* The *Instruction Register (IR)*: It decodes the instructions and select the machine ressources needed to execute them
* The *Arithmetic Logic Unit (ALU)*: It performs mathematical and logical operations
* The *Floating Point Unit (FPU)*: It performs floating-point operations

### Buses

The CPU needs to communicate with the outside world, and it does it through buses. There are three types:

* *Data Bus*: Used to transfer data from or to the memory
* *Address Bus*: Used to transfer the addresses of the memory or I/O devices. It is unidirectional
* *Control Bus*: Used to process the data

<a name="steps"/>

## Steps of the cycle

1. PC has address of next instruction
2. PC copied to the MAR
3. Lookup MAR and get contents. Copy contents into the MDR
4. Copy MDR contents into the IR
5. PC is then incremented by 1 (for the next instruction)
6. The instruction is decoded and then executed by sending signals to components
7. Repeat

<a name="sources"/>

## Sources

* [https://en.wikipedia.org/wiki/Instruction_cycle](https://en.wikipedia.org/wiki/Instruction_cycle)
* [http://www.wikiforu.com/2012/08/microprocessor-address-bus-data-bus-control-bus.html](http://www.wikiforu.com/2012/08/microprocessor-address-bus-data-bus-control-bus.html)
* [https://www.computerscience.gcse.guru/theory/fetch-execute-cycle](https://www.computerscience.gcse.guru/theory/fetch-execute-cycle)
* [https://www.youtube.com/watch?v=jFDMZpkUWCw](https://www.youtube.com/watch?v=jFDMZpkUWCw)
