---
layout:     post
title:      "Refactoring by Martin Fowler notes - Part 4"
date:       2018-01-25 07:16:00
summary:    "Bad smells in code." 
categories: refactoring martin fowler
---

Duplicated code  

Long method  

Large class  

Long parameter list  

Divergent change  
* When one class is commonly changed in different ways for different reasons.
* Identify everything that changes for a particular cause and use *Extract Class* to put them all together.  

Shotgun surgery  
* Everytime you make a change, you have to make a lot of little changes to a lot of different classes.
* Use *Move Method* and *Move Field* to put all changes in a single class.  

Feature envy  
Data clumps  
Primitive obsession  
Switch statements  
Parallel inheritance hierarchies  
Lazy class  
Speculative Generality  
...