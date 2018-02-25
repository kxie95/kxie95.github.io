---
layout:     post
title:      "Refactoring by Martin Fowler Part 8"
date:       2018-02-26 08:14:00
summary:    "A catalog of refactorings - Making method calls simpler" 
categories: refactoring
---

**Rename Method**  
* Code is for humans first, and computers second.
* Think of what the comment would be for the method and turn it into a name.
* Changing parameter order can also help.

**Add Paramter**  
* Actually advises against doing this unless you have no choice - it's hard to remember parameter lists.
* It's okay to do this, just be aware of alternatives like getting the info from existing parameters or passing in parameter objects.

**Separate Query form Modifier**  
* You have a method that return a value but also changes the state of an object.
* Create two methods, one for the query and one for the modification.
* In general it's good to just not make methods which have side effects.