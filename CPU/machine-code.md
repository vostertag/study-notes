# Machine Code

### Table of contents

[1. Introduction](#introduction)   
[2. Building the machine code](#building)  
[2. Sources](#source) 

<a name="introduction"></a>

## Introduction

Computers can only understand binary code (1s and 0s) and this is called the **machine code**.

Assembly code | Machine code |
--- | --- |
 ```Store 53``` | 000000110101 |
 
 Each instructions have a machine code equivalent, and the selection of instructions a computer can understand is called the **instruction set**. 
 
 <a name="building"></a>
 
 ## Building the machine code
 
 Most of the instructions have two main parts:
 
 * **Opcode**: the code of the instruction
 * **Operand**: the data or the adress
 
 For example:
 ``` LD A, 01H ``` asks the computer to load into the register A, the number 01 (in Hexadecimal).
 When executing this command, the assembler would translate this instruction into a machine code where ``` LD A ``` would be the **Opcode** as it is the instruction we are asking the machine to perform and ``` 01H ``` would be the **Operand**, as it is the number we would like to load: 
 
 Op Code | Operand |
--- | --- |
 00111110 | 0000001 |
 
 But we might not always need the Operand part. For example ``` INC A ```, which means to add one to the register A, would only need an Op Code, since the operand is implied here...

 Op Code | 
--- | 
 00111100 |
 
 <a name="source"></a>
 
 ## Sources
 
 * [https://www.youtube.com/watch?v=Mv2XQgpbTNE](https://www.youtube.com/watch?v=Mv2XQgpbTNE)
 * [https://en.wikibooks.org/wiki/A-level_Computing/AQA/Computer_Components,_The_Stored_Program_Concept_and_the_Internet/Machine_Level_Architecture/Machine_code_and_processor_instruction_set](https://en.wikibooks.org/wiki/A-level_Computing/AQA/Computer_Components,_The_Stored_Program_Concept_and_the_Internet/Machine_Level_Architecture/Machine_code_and_processor_instruction_set)
 
 
