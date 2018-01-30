---
layout:     post
title:      "Refactoring by Martin Fowler notes - Part 4"
date:       2018-01-25 07:16:00
summary:    "Bad smells in code." 
categories: refactoring martin fowler
---

**Duplicated code**  

**Long method**  

**Large class**  

**Long parameter list**  

**Divergent change**  
* When one class is commonly changed in different ways for different reasons.
* Identify everything that changes for a particular cause and use *Extract Class* to put them all together.  

**Shotgun surgery**  
* Everytime you make a change, you have to make a lot of little changes to a lot of different classes.
* Use *Move Method* and *Move Field* to put all changes in a single class.  

**Feature envy**  
* When a method is more interested in another class than the one it's actually in.
* Most common focus of envy is the data.
* Use the *Move Method*. Sometimes *Extract Method* when if only part of it suffers from envy.
* Rule of thumb is to put things together that change together.  

**Data clumps**  
* 3 or 4 data items that hang together - in fields, parameters and classes.
* Make them into an object. 
* If you deleted one of the values, would the others make sense? If yes, make an object!

**Primitive obsession**  
* Primitives are just building blocks. Objects give you a better abstraction.

**Switch statements**  
**Parallel inheritance hierarchies**  
**Lazy class**  
**Speculative Generality**  
...