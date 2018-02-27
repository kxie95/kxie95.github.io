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

**Separate Query from Modifier**  
* You have a method that return a value but also changes the state of an object.
* Create two methods, one for the query and one for the modification.
* In general it's good to not make methods which have side effects because then you can call the function over and over and have expected results.

**Paramterize Method**  
* Several methods do similar things but with different values contained in the method body.
* Create one method that uses a parameter for the different values.
* Removes duplicate code and increases flexibility.

**Replace Parameter with Explicit Methods**  
* You have a method that runs different code depending on the values of a parameter.
* Create a separate method for each value of the parameter.
* Gives your class a clearer interface so then the person using your interface doesn't have to look for the methods AND set a valid paramter.

**Preserve Whole Object**  
* You are getting several values from an object and passing these values as parameters in a method call.
* Send the whole object instead.
* If the method needs a whole new set of values later, we don't have to change the parameters.
