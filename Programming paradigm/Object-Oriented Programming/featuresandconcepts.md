# Features and Concepts of Object-Oriented Programming

### Table of Contents

[1. Shared with other paradigms](#shared-with-other-paradigms)  
[2. Objects and classes](#objects-and-classes)  

## Shared with other paradigms

* **Variables**, that can store the data.
* **Procedures** (functions), that take an input and generate an input for it.

## Objects and classes

A **class** is a template for an object that has **initial values for state (member variables)** and **implementations of behavior (member functions or methods)**. An **object** is simply an instance of a class.

![Class](https://upload.wikimedia.org/wikipedia/commons/1/18/Oop-uml-class-example.png)

## Encapsulation

Concept that **binds together the data and functions that manipulate the data**, and that **keeps both safe from outside interference and misuse**. For example, a class that never lets the user access its data directly

## Composition

**Composition** is when an object **contain other objects in their instance variables**. In order to spot when to use composition, it is good to use the "has" method. For example: A car **has** a wheel.

## Inheritance

When a class **inherits** from an other, it gets all of his parent's datas and methods. This allows classes to be arranged in a hierarchy that represents "is-a-type-of" relationships. For example: A cat **is a type of** animal.

![Inheritance](https://docs.oracle.com/javase/tutorial/figures/java/concepts-bikeHierarchy.gif)

There is a doctrine of **composition over inheritance**, advocating implementing has-a relationships using composition instead of inheritance. For example, instead of inheriting from class Person, class Employee could give each Employee object an internal Person object.

## Abstract class 

An **abstract class cannot be instantiated into objects**; they exist only for the purpose of inheritance into other "concrete" classes which can be instantiated.

## Interface

