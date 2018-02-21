---
layout:     post
title:      "Refactoring by Martin Fowler Part 6"
date:       2018-02-09 08:38:00
summary:    "A catalog of refactorings - Organising Data" 
categories: refactoring
---

**Split temporary variable**  
* What: Temporary variable assigned more than once.  
* Fix: Make a separate variable for each assignment.  
* Why: The fact that they are set more than once means they have more than one responsibility. Confusing for the reader.  

**Replace Method with Method Object**  
* What: Long method that uses local variables in a way that you can't extract out methods.  
* Fix: Turn method into an object with the local variables as fields. 

**Introduce Local Extension**  
* What: A server class you are using needs several additional methods, byt you can't modify the class.
* Fix: Create a new class that contains these extra methods. Make this extension class a subclass or a wrapper of the original.

**Encapsulate Collection**  
* What: A method returns a collection.
* Fix: Make it return a read-only view and provide add/remove methods.  
* Why: Should not allow the collection to be returned because that allows the client to manipulate it however they want. It reveals too much about the internal structure of the class and how it holds its data.  

**Replace Record with Data Class**  
* What: You need to interface with a record structure in a traditional programming environment.
* Fix: Make a dumb data object for the record.
* Why: Creates an abstraction for external elements (eg. database record) which creates a better separation of concerns.
 

