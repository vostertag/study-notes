# Features and Concepts of Object-Oriented Programming

### Table of Contents

[1. Shared with other paradigms](#shared-with-other-paradigms)  
[2. Objects and classes](#objects-and-classes)    
[3. Encapsulation](#encapsulation)  
[4. Composition](#composition)  
[5. Inheritance](#inheritance)  
[6. Abstract class](#abstract-class)  
[7. Interface](#interface)  
[8. Association](#association)  
[9. Aggregation](#aggregation)  
[10. Polymorphism](#polymorphism)  
[11. Open recursion](#open-recursion)  
[12. Sources](#sources)
 
## Shared with other paradigms

* **Variables**, that can store the data.
* **Procedures** (functions), that take an input and generate an input for it.

## Objects and classes

A **class** is a template for an object that has **initial values for state (member variables)** and **implementations of behavior (member functions or methods)**. An **object** is simply an instance of a class.

![Class](https://upload.wikimedia.org/wikipedia/commons/1/18/Oop-uml-class-example.png)

```cpp
class Player
{
    Text Name
    Text Role
 
    Pass (Player teamMate)
    {
        // body of the method
    }
}
```

## Encapsulation

Concept that **binds together the data and functions that manipulate the data**, and that **keeps both safe from outside interference and misuse**. For example, a class that never lets the user access its data directly

## Composition

**Composition** is when an object **contain other objects in their instance variables**. In order to spot when to use composition, it is good to use the "has" method. For example: A car **has** a wheel.

```cpp
class Arena
{
    Text Name
    Integer Capacity
}
 
class Team
{
    Arena HouseOfTheTeam
 
    EvaluateArena()
    {
       // if arena is too small for our league
       HouseOfTheTeam.Destroy()
       // create a new Arena
       HouseOfTheTeam = new Arena        
    }
}
```

## Inheritance

When a class **inherits** from an other, it gets all of his parent's datas and methods. This allows classes to be arranged in a hierarchy that represents "is-a-type-of" relationships. For example: A cat **is a type of** animal.

![Inheritance](https://docs.oracle.com/javase/tutorial/figures/java/concepts-bikeHierarchy.gif)

There is a doctrine of **composition over inheritance**, advocating implementing has-a relationships using composition instead of inheritance. For example, instead of inheriting from class Person, class Employee could give each Employee object an internal Person object.

```cpp
class Person
{
    Integer Salary
    Text Name
}
 
class Coach : parent Person
{
    AskForARaise()
    {
        if Salary < 1000
             // request more money
    }  
}
```

## Abstract class 

An **abstract class cannot be instantiated into objects**; they exist **only for the purpose of inheritance** into other "concrete" classes which can be instantiated.

## Interface

An alternative to inheritance for **two unrelated classes** to communicate with each other. An interface **defines methods and (often, but not always) values**. **Every class that implement the interface must provide a concrete method for each method of the interface**.

The **difference between an interface and an abstract class**: 

Interface | Abstract Class |
---| ---|
Only can have constants and methods stubs (methods without a body) | Can have constants, members, method stubs and defined methods |
Methods must be ```public``` | Methods and members can be defined with any visibility |
A class can implement multiple interfaces | A class can only implement one abstract class |
Child class must implement methods with the same visibility (```public```) | Child class can implement methods with the visibility they want |

```cpp

interface Ejectable
{
    Ejection()
}
 
class Player : implement Ejectable
{
    Ejection()
    {
        // storm out of the field screaming
    }
}
 
class Coach : implement Ejectable
{
    Ejection()
    {
        // take your cellphone to talk with your assistant
    }
}
```

## Association

An association simply **describes any kind of working relation**. The two object are instances of **completely unrelated classes**. They just collaborate to accomplish their own goals.

```cpp
class Audience
{
    Boolean Cheering
 
    Cheer()
    {
         Cheering = true
    }
 
    StopCheer()
    {
         Cheering = false
    }
}
 
Audience HomePeople = new Audience
 
class Player
{
    ListenToThePeople()
    {
        if HomePeople.Cheering = true
            // improve ability
    }
}
```

## Aggregation

When an object **belongs to an other one**, but they are still potentially independent. 

```cpp
class Audience
{
    Boolean Cheering
 
    Cheer()
    {
         Cheering = true
    }
 
    StopCheer()
    {
         Cheering = false
    }
}
 
Audience HomePeople = new Audience
 
class Player
{
    ListenToThePeople()
    {
        if HomePeople.Cheering = true
            // improve ability
    }
}
```

## Polymorphism

Polymorphism describes a **pattern in object oriented programming in which classes have different functionality while sharing a common interface**.



## Open recursion

The ability for one method body to **invoke another method of the same object via a special variable called self or this**.

## Sources

* [https://tomassetti.me/oops-concepts/#classParagraph](https://tomassetti.me/oops-concepts/#classParagraph)
* [https://stackoverflow.com/questions/1031273/what-is-polymorphism-what-is-it-for-and-how-is-it-used](https://stackoverflow.com/questions/1031273/what-is-polymorphism-what-is-it-for-and-how-is-it-used)
* [https://stackoverflow.com/questions/1913098/what-is-the-difference-between-an-interface-and-abstract-class](https://stackoverflow.com/questions/1913098/what-is-the-difference-between-an-interface-and-abstract-class)
* [https://en.wikipedia.org/wiki/Object-oriented_programming](https://en.wikipedia.org/wiki/Object-oriented_programming)
