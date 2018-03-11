# Symmetric Ciphers

### Table of Contents

[1. Introduction](#introduction)  
[2. Block Cipher](#block-cipher)
* [2.1. Feistel Block Cipher](#feistel-block-cipher)  
* [2.2. DES: Data Encryption Standard](#des-data-encryption-standard)  
* [2.3. AES: Advanced Encryption Standard](#aes-advanced-encryption-standard)  

[3. Stream Cipher](#stream-cipher)  
[4. Sources](#sources)  

## Introduction

**Symmetric ciphers** uses **the same key to encrypt data as it does to decrypt data**. The ciphers seen in the [introduction to cryptography](https://github.com/vostertag/study-notes/blob/master/Cryptography/history.md) are symmetric ciphers. The most popular of these is **Advanced Encryption Standard (AES)**.

![Symmetric Cipher](https://ds055uzetaobb.cloudfront.net/image_optimizer/85cba3419843e53986bb5d304dadeda9367568db.png)

Today, there are mainly two types of symmetric ciphers:

## Block Cipher

The **block cipher** take in n bits of plaintext and n bits of key to produce n bits of ciphertext. The are known as block ciphers because they operate on blocks of n x n bits at a time. The cipher works by **taking a relatively simple function and iterating it several times** (it is the **round function**).

These iterations combine **substitutions** and **permutations** (called a **substitution–permutation networks** (SPN)). The substitution allows to create **Shannon's confusion**, that is to say making the relationship between the key and the ciphertext as complex and as involved as possible. The permutation allows to create a **diffusion**, that is to say if we change a single bit of the plaintext, then (statistically) half of the bits in the ciphertext should change, and similarly, if we change one bit of the ciphertext, then approximately one half of the plaintext bits should change.

### Feistel Block Cipher

This is an approach on how to build a block cycle.

The **encryption process** consists of **multiple rounds of processing of the plaintext**, each round consisting of a substitution step followed by a permutation step.

![Feistel](https://www.tutorialspoint.com/cryptography/images/feistel_structure.jpg)

The plaintext is divided into a **left half** and a **right half**. In each round, only the left half goes through the round function that depends on the right half and the encryption key. The result is then **XORed** (that is to say, we perform a XOR bitwise operation, which is better than a AND or OR, see why [here](https://www.khanacademy.org/computing/computer-science/cryptography/ciphers/a/xor-and-the-one-time-pad)). Finally, before going to the next iteration, the two halves are swapped.

The **decryption process** is pretty much similar: the ciphertext block is fed into the start of the Feistel structure and then the process thereafter is exactly the same as described in the given illustration.

The difficult part of designing a Feistel Cipher is selection of round function ‘f’.

### DES: Data Encryption Standard

DES is an implementation of a Feistel Cipher. It uses a **16 rounds Feistel structure**. The block size is **64-bit** and the key length is of **56 bits**.

![DES](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/DES-main-network.png/250px-DES-main-network.png)

The DES performs an **initial permutation (IP)** and a **final permutation (FP)** that are inverses. In the middle, there are 16 rounds of processing performed.

This was used in the 1970's, but is now not secured, as it can be broken by brute-force, as the key is too small.

### AES: Advanced Encryption Standard

One way to improve the DES was the **Triple DES**, cascading three instances of DES with distinct keys, making it much secure. But this process is too slow. Instead, the AES is widely used nowadays.

The AES is **not** a Feistel Cipher. It has **128-bit data** and **128, 192 or 256-bit keys**. The number of rounds of processing depends on the size of the key (10, 12 or 14 rounds). And each of these rounds **uses a different 128-bit round key**, which is calculated from the original AES key.

The input is arranged in a **4 x 4 matrix**. This matrix, called the **state**, will be modified as the algorithm progresses

![AES](http://nevonprojects.com/wp-content/uploads/2015/06/aes-image.png)

```AddRoundKey``` takes the current state and XORs it with the key for this particular round. The result is the new state.

```SubBytes``` is one of the substitution functions of the specific AES implementation.

```ShiftRows``` shifts the bytes in each row with respect to each other. This step is done to ensure the columns are not linearly independent.

```MixColumns``` multiplies each column of the state by an invertible function, a fixed polynomial. 

## Stream Cipher

In a **stream cipher**, each plaintext digit is **encrypted one at a time with the corresponding digit of the keystream**, to give a digit of the ciphertext stream.

Some of the ciphers in the introduction are stream ciphers.

## Sources

* [https://brilliant.org/wiki/symmetric-ciphers/](https://brilliant.org/wiki/symmetric-ciphers/)
* [https://en.wikipedia.org/wiki/Block_cipher#Iterated_block_ciphershttps://en.wikipedia.org/wiki/Block_cipher#Iterated_block_ciphers](https://en.wikipedia.org/wiki/Block_cipher#Iterated_block_ciphers)
* [https://en.wikipedia.org/wiki/Stream_cipher](https://en.wikipedia.org/wiki/Stream_cipher)
* [https://www.tutorialspoint.com/cryptography/feistel_block_cipher.htm](https://www.tutorialspoint.com/cryptography/feistel_block_cipher.htm)
* [https://www.tutorialspoint.com/cryptography/advanced_encryption_standard.htm](https://www.tutorialspoint.com/cryptography/advanced_encryption_standard.htm)
* [https://www.tutorialspoint.com/cryptography/block_cipher.htm](https://www.tutorialspoint.com/cryptography/block_cipher.htm)
* [https://www.youtube.com/watch?v=ySZvE9vOfEQ](https://www.youtube.com/watch?v=ySZvE9vOfEQ)
