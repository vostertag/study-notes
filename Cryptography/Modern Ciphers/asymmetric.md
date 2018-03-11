# Asymmetric Ciphers

### Table of Contents

[1. Introduction](#introduction)  

## Introduction

A major problem with [symmetric ciphers](https://github.com/vostertag/study-notes/blob/master/Cryptography/Modern%20Ciphers/symmetric.md) is that the two persons wanting to communicate must meet to share the **key** that must be used for the encryption/decrytion. But on the internet, for example, this cannot be done. Moreover, having one key per communication would be really difficult to manage. Instead, we must use **asymmetric ciphers**, that don't require a secret key to be exchanged.

Instead, it uses two types of keys: **public keys** that everyone will be able to know and **private keys** that only the owner knows. This accomplishes two functions: **authentication**, where the public key verifies a holder of the paired private key sent the message, and **encryption**, where only the paired private key holder can decrypt the message encrypted with the public key.

## 
