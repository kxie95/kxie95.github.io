---
layout:     post
title:      "Refactoring by Martin Fowler - Notes"
date:       2017-12-22 09:00:00
summary:    "" 
categories: refactoring martin fowler
---

## How to go about refactoring?  
* Write solid tests
* Decompose and redistribute (for big methods)
* Do changes in small steps  

**Test, small change, test, small change, test...**  

## Principles in refactoring
**Three strikes and you refactor**  
First time you do something, second time you do something similar, third time you do something similar again, refactor.  

**Refactor when you add function**  
Helps you add the function more easily.  

**Refactor when you need to fix a bug**  
Code was not clear enough for you to see the bug.    

**Refactor as you do a code review**  
Useful suggestions.  

## Techniques
**Renaming**  
* Easier to understand the code as you're trying to refactor it.

**If a method does not use any data from its class, it probably belongs somewhere else**  
* Move contents to its proper class and create a new method.
* Call the new method from the old method.
* Replace if tests pass.  

**Replace temp variable with query**  
* Eg. A temp variable which accumulates.
* Extract this accumulation into its own method.
* Call that method and remove all instances of the temp variable.
* May reduce performance but cleaner code.  