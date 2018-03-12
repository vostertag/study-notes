# Attacks on hash functions

### Table of Contents

[1. Introduction](#introduction)  
[2. Collision Attack](#collision-attack)  
[3. Rainbow Table](#rainbow-table)  
[4. Sources](#sources)

## Introduction

I have already talked about hash functions [here](https://github.com/vostertag/study-notes/blob/master/Data%20Structures/Hash%20Table/hashtable.md). Here I will focus on attacks that can be used on hash functions and ways to avoid them.

## Collision Attack

A **Hash Collision Attack** is an attempt to find **two input strings of a hash function that produce the same hash result**. As seen in previous notes, hash functions will always have some collisions. It is inevitable. This can be exploited. For example, files are using hashes to prove their integrity. With some hash functions, it is possible for the attacker to change a file into a malicious one and mangage to get the same hash result. MD5 and SHA-1 are algorithms that can be broken that way.

![collision-attack](https://learncryptography.com/assets/content/images/HashCollisionAttack.jpg)

## Rainbow Table

A **rainbow table** is a **large database that contains a large number of a hash function’s inputs and corresponding outputs**. A rainbow table makes brute forcing a password hash much easier, by removing the most computationally complicated part of a brute force – performing the hash function itself. With all of the values already computed, it’s simplified to just a simple search-and-compare operation on the table.

So if one stores a password in a database using just a hash function, it might possible to find the password thanks to a rainbow table.

![Rainbow Table](http://wiki.cas.mcmaster.ca/images/f/f0/Hash_table_example.jpg)

The best way to avoid it is **password salting**. A **salt** is a random string of character that is different for every single user. When the user registers, the password is stored using its hash to which the salt is added. Now, if someone were to try to compare the database password hashes with a list of common password hashes – none of the hashes would match, even if users had used common passwords in the attackers list. The salt completely changes the output of the hash function, meaning that an attacker would have to brute force the password of each user individually, effectively eliminating the benefit of a rainbow table. 

## Sources

* [https://learncryptography.com/encryption#hash-functions](https://learncryptography.com/encryption#hash-functions)
* [https://www.youtube.com/watch?v=8ZtInClXe1Q](https://www.youtube.com/watch?v=8ZtInClXe1Q)
* [https://www.youtube.com/watch?v=b4b8ktEV4Bg](https://www.youtube.com/watch?v=b4b8ktEV4Bg)
 
 
