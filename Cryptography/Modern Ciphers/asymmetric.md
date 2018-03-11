# Asymmetric Ciphers

### Table of Contents

[1. Introduction](#introduction)  
[2. RSA Cryptosystem](#rsa-cryptosystem)
* [2.1. Euler's totient function](#eulers-totient-function)
* [2.2. Key Generation](#key-generation)
* [2.3. Encryption](#encryption)
* [2.4. Decryption](#decryption)
* [2.5. Why it is effective](#why-it-is-effective)

[3. Sources](#sources)

## Introduction

A major problem with [symmetric ciphers](https://github.com/vostertag/study-notes/blob/master/Cryptography/Modern%20Ciphers/symmetric.md) is that the two persons wanting to communicate must meet to share the **key** that must be used for the encryption/decrytion. But on the internet, for example, this cannot be done. Moreover, having one key per communication would be really difficult to manage. Instead, we must use **asymmetric ciphers**, that don't require a secret key to be exchanged.

Instead, it uses two types of keys: **public keys** that everyone will be able to know and **private keys** that only the owner knows. This accomplishes two functions: **authentication**, where the public key verifies a holder of the paired private key sent the message, and **encryption**, where only the paired private key holder can decrypt the message encrypted with the public key.

In a public key encryption system, **any person can encrypt a message using the receiver's public key**. That encrypted message **can only be decrypted with the receiver's private key**.

![Public key](https://cs.wellesley.edu/~cs110/reading/cryptography-files/public.jpg)

## RSA Cryptosystem

This system is widely used. It was invented by three scholars Ron Rivest, Adi Shamir, and Len Adleman and hence, it is termed as RSA cryptosystem and based on the practical difficulty of the factorization of the product of two large prime numbers, the "**factoring problem**".

### Euler's totient function

**Euler's totient function**, or the **Phi function**, counts the positive integers up to a given integer n that are coprime to n (have no common factors with it). A prooperty of this function is that φ(mn) = φ(m)φ(n) and that  φ(m) = (m-1) if m is a prime number (as prime factors have no factors greater than one).

**Example**:

```  φ(8) = 4 ``` because 1, 3, 5, 7 are coprimes of 8...

### Key Generation

* Select **two large prime numbers**: p and q.
* Calculate **n = p x q** (n must be a minimum of 512 bits for it to be unbreakable).
* The derived number **e must be between 1 and φ(pxq)** ((p-1)(q-1)) and be a **coprime** of φ(pq).
* **(n,e) are made public** (difficulty in factorizing a large prime number ensures that attacker cannot find in finite time the two primes (p & q) used to obtain n).
* The private key d must solve **d x e ≡ 1 (mod φ(n))**.

### Encryption

Bob wants to send a message to Alice. First Bob turns his message into an integer **m that must be smaller than n** using a **padding scheme**, which makes sure the same plaintext won't always be encrypted the same way for example, making the RSA more secure.

The ciphertext c is obtained like this:

``` c ≡ m^e ( mod n ) ```

### Decryption

Alice can get the original message using her private key: 

``` c^d ≡ (m^e)^d ≡ m ( mod n ) ```

### Why it is effective

For an attacker to find the private key d, he must find φ(n). Without knowing p and q, this takes too much time using brute force to be viable (as long as n is large enough).

## Sources

* [https://www.tutorialspoint.com/cryptography/public_key_encryption.htm](https://www.tutorialspoint.com/cryptography/public_key_encryption.htm)
* [https://en.wikipedia.org/wiki/Public-key_cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography)
* [https://www.youtube.com/watch?v=oOcTVTpUsPQ](https://www.youtube.com/watch?v=oOcTVTpUsPQ)
* [https://www.khanacademy.org/computing/computer-science/cryptography/modern-crypt](https://www.khanacademy.org/computing/computer-science/cryptography/modern-crypt/v/rsa-encryption-part-4)

