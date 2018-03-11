# Introduction: History of Cryptography

### Table of contents

[1. Introduction](#introduction)  
[2. The Caeser cipher](#caeser-cipher)  
[3. The Polyalphabetic cipher](#the-polyalphabetic-cipher)  
[4. The One-time pad](#the-one-time-pad)  
[5. The Enigma encryption machine](#the-enigma-encryption-machine)  
[6. Sources](#sources)

## Introduction

Cryptography has been around for thousands of year, mainly because of wars and the need to transmit messages that, if intercepted by an  adversary, would not make any sense. To do so, the message must be **encrypted**, which is to say converted into a code, thanks to a **cipher**, which is the code used to do so. This cipher must be known by the one receiving the message for it to be **decrypted**.

This note will present some ways of encrypting messages through time.

## The Caeser cipher

This method is one of the simplest, invited by Julius Caeser (hence the name).

It is a type of substitution cipher in which **each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet**.

So for example, using a shift of 23 (which is the **key** to use to decrypt this cipher), the alphabet becomes:

```
Plain:    ABCDEFGHIJKLMNOPQRSTUVWXYZ
Cipher:   XYZABCDEFGHIJKLMNOPQRSTUVW
```  

Breaking the cipher can be done via **brute force** (testing all possibilities) as there are only 26 shifts possible...
In order to break this cipher more efficiently, one must use a **frequency analysis**. Each language has some sort of **fingerprint** attached to it: **the distribution of letters in a typical sample of a language text**. Here are the frenquencies of each letter in an English text:

![Frequency English language](https://upload.wikimedia.org/wikipedia/commons/4/41/English-slf.png)

To break the cipher, one just has to count the frequency of each letter and recreate this graph and check by how far the fingerprint has shifted. The number will be the key that has been used...

## The Polyalphabetic cipher

In order to make a harder cipher, one must **flatten the fingerprint**. The Polyalphabetic cipher is one way to do that. Here is an example of how a polyalphabetic cipher works.

The encryptor and decryptor must agree on a **keyword** before hand. What we really care about is the letters position in the alphabet. These number will be used to determined the shift in the Caeser cipher.

```
Keyword: LEMON
In the alphabet: 12 5 13 15 14
```

Then, to encrypt a message, each letter of the message is assigned the positions of the letters of the keyword in a cycle: 

```
To encrypt: Hello, how are you?
Number assigned: 12 5 13 15 14,   12 5 13   15 14 12   5 13 15?
```

Finally, we use the number below each letter of the message for the shift to use. This allows to use multiple shift instead of just one.

```
Plaintext: Hello, how are you?
Encrypted: TJYAC, TTJ PFQ DBJ?
```

That way, the fingerprint is flatten, making a codebreaker's job much harder, but not impossible. As we use a keyword with a limited number of letters, there is a repetition in the cipher used in the encryption. A codebreaker would have to check the frequency distribution of different intervals (here, of every fifth letter), the fingerprint would then appear just like we have seen before.

In order for this cipher to be stronger, a larger keyword must be used. But in every case, it will not be impossible to break, it will just take a longer time.

## The One-time pad

How to make sure there is no leak of information? No way for an attacker to break the cipher? The answer is **randomness**. 

The one-time pad consists of choosing shifts **randomly** in the polyalphabetic cipher with the number of shifts equal to the number of letters in the message to encrypt. This way, there will never be a repetitive pattern and the fingerprint left behind will be completely flatten. There is no way for someone to break this cipher. We have reached **perfect secrecy** (when no matter what, a blind guess is the best one can make).

## The Enigma encryption machine

The Enigma machine is an encryption machine used by the German military during World War II. The idea was to **automate the one-time pad**.

![Enigma Machine](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bd/Enigma_%28crittografia%29_-_Museo_scienza_e_tecnologia_Milano.jpg/1024px-Enigma_%28crittografia%29_-_Museo_scienza_e_tecnologia_Milano.jpg)

Of course, it is impossible to get truly random numbers, as a machine's actions are **predictable and repeatable**. So what they did at the time is having three rotors which cycles would take a very long time to reapeat themselves. These rotos determined the shift to be used for a letter and after it being typed, a rotor would change his position, making sure that the shift would never be the same. 

In order to decrypt a message, a **key** has to be passed: the initial position of the rotors. The Germans even increased the number of keys (the **key space**) to make it even more difficult to break, by adding a 4th rotor for example.

The first main weakness of this machine is the operators that would have to select a random initial setting. The mistake was to rotate the rotors only a few clicks from the initial state or reusing some combinations, which destroyed the uniform distribution of the initial rotors position. This allowed the allies to reverse-engineer the wiring used in the machine.

The second error is that a letter would never be encrypted to itself. So if you see a "L" in the encrypted message, you know that "L" was not the initial letter. This allowed the allies to create a code-breaker machine which would test different settings of rotors. It also used the fact that common words always were in the encrypted message. Using these words (known as **cribs**), the machine could find possible key settings in minutes.

## Sources

* [https://www.khanacademy.org/computing/computer-science/cryptography](https://www.khanacademy.org/computing/computer-science/cryptography)
