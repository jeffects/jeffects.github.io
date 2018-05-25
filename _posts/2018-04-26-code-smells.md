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

An indication that your code might not be as changeable is called a code smell. Code smell was first introduced by Kent Beck while helping Martin Fowler with his book, [Refactoring](https://martinfowler.com/books/refactoring.html).  In the book Refactoring, Martin Fowler defined **code smell** as a “surface indication that usually corresponds to a deeper problem in the system.” He also lists 23 types of code smells, each with a prescriptive refactoring.

Reading **Refactoring** is like reading recipe book. It is great when you know what you want to cook but can be a little daunting if you are reading to learn how to cook a particular type of food. Luckily for us, Sandi Metz in her 2016 presentation classifies the 23 types of code smells into 5 different categories.  The following lists the categories and their code smells.

**Note**: RR refers to the book [Refactoring Ruby](https://martinfowler.com/books/refactoringRubyEd.html) and the numbers represents the page number.


## Bloaters
Bloaters are code, methods and classes that have increased to such gargantuan proportions that they are hard to work with. Usually these smells do not crop up right away, rather they accumulate over time as the program evolves.  They make code bigger than they need to be in the places you use them.


* Long Method (RR74)
* Large Class (RR76)
* Data Clumps (RR79)
  * Data that is always together (parameters)
* Long Parameter List (RR76-77)
* Primitive Obsession (RR79)
  * Instance of a base class (String, hash, number)
  * Receivers use conditions to know what to do with them
  * Need smarter objects
 

## Tool Abusers
Ideas available in OOP that you can misuse.  All these smells are incomplete or incorrect application of object-oriented programming principles.


* Switch Statements (RR80)
  * Basically conditionals
* Refused Bequest (RR84-85)
 * Subclass of something but doesn't do request
* Alternative Classes w/ Different Interfaces (RR83)
* Temporary Field (RR82)

## Change Preventers
These smells mean that if you need to change something in one place in your code, you have to make many changes in other places too. Program development becomes much more complicated and expensive as a result.


* Divergent Change (RR77)
  * Need to make a change so we add a conditional
* Shotgun Surgery (RR78)
 * Change a concept and have to edit code in a bunch of places
 * Parallel Inheritance Hierarchies (RR81)

## Dispensables
A dispensable is something pointless and unneeded whose absence would make the code cleaner, more efficient and easier to understand.


* Lazy Class (RR81)
* Speculative Generality (RR81)
* Data Class (RR84)
* Duplicated Code (RR74)

## Couplers
All the smells in this group contribute to excessive coupling between classes or show what happens if coupling is replaced by excessive delegation.


* Feature Envy (RR78-79)
* Inappropriate Intimacy (RR83)
* Message Change (RR82)
* Middle Man (RR83)


In general, being cognizant of code smells and the tools available to fix them will result in your code being easier to change in the future.
