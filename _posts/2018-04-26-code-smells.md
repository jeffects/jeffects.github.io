---
title: Code Smells
layout: post
date: '2018-05-24 22:48:00'
tag:
- code smells
- programming
- software engineering
- refactoring
category: blog
description: First post
author: Jeffects
---

# Code Smells
I often tell my colleagues that the most essential thing in Software Engineering is **changeability**. Code that is optimized to change is code that is clean, readable, and easy to understand.

An indication that your code might not be as changeable is called a **code smell**.  Code smell was first introduced by Kent Beck while helping Martin Fowler with his book, [Refactoring](https://martinfowler.com/books/refactoring.html).  In the book Refactoring, Martin Fowler defined code smell as a “surface indication that usually corresponds to a deeper problem in the system.” He also lists 23 types of code smells, each with a prescriptive refactoring.

Reading **Refactoring** is like reading recipe book. It is great when you know what you want to cook but can be a little daunting if you are reading to learn how to cook a particular type of food. Luckily for us, Sandi Metz in her 2016 presentation, [Get a Whiff of This](https://www.youtube.com/watch?v=PJjHfa5yxlU), she classifies the 23 types of code smells into 5 different categories.  The following lists the categories and their code smells.

**Note**: RR refers to the book [Refactoring Ruby](https://martinfowler.com/books/refactoringRubyEd.html) and the numbers represents the page number.


## Bloaters
Bloaters are code, methods and classes that have increased to such gargantuan proportions that they are hard to work with. Usually these smells do not crop up right away, rather they accumulate over time as the program evolves.  They make code bigger than they need to be in the places you use them.


* **Long Method** (RR74)
  * A method that contains too many lines of code (LOC)
* **Large Class** (RR76)
  * A class that contains too many methods, LOC, or does too much.  AKA the God
    class
* **Data Clumps** (RR79)
  * Group of variables which are passed around together, usually as parameters
* **Long Parameter List** (RR76-77)
  * More than three or four parameters for a method
* **Primitive Obsession** (RR79)
  * Use of primitives (string, hash, number) instead of small smarter objects (date ranges, currency, etc)
 

## Tool Abusers
Ideas available in OOP that you can misuse.  All these smells are incomplete or incorrect application of object-oriented programming principles.


* **Switch Statements** (RR80)
  * Basically too many conditionals or complex conditions
* **Refused Bequest** (RR84-85)
  * Subclass of something but doesn't do the request
  * Usually inheritances between classes only to use some methods but are really
   of different types
* **Alternative Classes w/ Different Interfaces** (RR83)
  * Two or more classes with identical methods but have different names
* **Temporary Field** (RR82)
  * Fields populated with values only under certain circumstances and are often
    left empty and unused


## Change Preventers
These smells mean that if you need to change something in one place in your code, you have to make many changes in other places too. Program development becomes much more complicated and expensive as a result.


* **Divergent Change** (RR77)
  * Attempt to change one method in a class requires you to change unrelated methods also
* **Shotgun Surgery** (RR78)
  * Modification requires many small changes to different classes
  * Opposite of Divergent change
* **Parallel Inheritance Hierarchies (**RR81)
  * Creating a subclass leads to creating another subclass for another class

## Dispensables
A dispensable is something pointless and unneeded whose absence would make the code cleaner, more efficient and easier to understand.


* ** Lazy Class** (RR81)
  * A class that is no longer valid or has any useful functionality but is still
    in the codebase
* **Speculative Generality** (RR81)
  * Speculative code that is created to anticipate the future but never used
* **Data Class **(RR84)
  * Class that only contains fields and simple methods accessing them
* **Duplicated Code** (RR74)
  * Identical code

## Couplers
All the smells in this group contribute to excessive coupling between classes or show what happens if coupling is replaced by excessive delegation.


* **Feature Envy** (RR78-79)
  * A class/method that accesses data of another object more than its own data
* **Inappropriate Intimacy** (RR83)
  * Class that uses internal fields and methods of another class
* **Message Chains** (RR82)
  * Methods that calls other methods in a chain.
  * Breaks the Law of Demeter
* **Middle Man** (RR83)
  * A class that its sole purpose is to only delegate work to another class

## Conclusion

  In general, being cognizant of code smells and the tools available to fix them will result in your code being easier to change in the future.  Code reviews are also a great place to exercise practicing recognizing code smells and addressing them!