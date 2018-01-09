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