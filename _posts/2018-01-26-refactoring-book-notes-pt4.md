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
* Switch statements are a form of duplication. This can usually be solved with polymorphism.

**Parallel inheritance hierarchies**  
* Everytime you make a subclass of one class, you also have to make a subclass of another. 
* Don't really know when this would happen?

**Lazy class**  
* A class that isn't doing enough to pay for itself.
* Eliminate it by collapsing the hierarchy or inlining a class.  

**Speculative Generality**  
* Thinking you might need something so you implement a more complex solution than you should.
* eg. unnecessary delegations, hooks, abstract classes not doing much, only test cases using the class.  

**Temporary Field**  
* Instace field only set in certain circumstances (you expect an object to need all its variables).
* Extract Class out of these orphan variables and put all the code that concerns the variables with it.

**Message Chains**  
* When a client asks one object for another object, which the client asks for yet another object, which the client then asks for yet another object and so on.
* Client is coupled to the structure of the navigation. Any change to the intermediate relationships causes the client to have to change.
* Fix using extract method to take the piece of code that uses it and then move method to push it down the chain.  

**Middle man**  
* Encapsulation often comes with delegation. (eg. ask person if they're free for a meeting, they delegate to a calendar (but you don't care what they use)).
* This can be taken too far - you look at a class and half its methods are delegating to another class.
* In this case, remove the middle man if possible, or inline the method in the caller.  

**Inappropriate Intimacy**  
* "Sometimes classes become far too intimate and spend too much time delving in each others' private parts."
* "Overintimate classes need to be broken up as lovers were in ancient days".  

**Alternative Classes with Different Interfaces**  
* Rename any classes that do the same thing but have different names.
* Move methods into classes until the protocols are the same.  

**Data class**  
* Are these bad? This book suggests that they should develop into objects with responsibilities.  
