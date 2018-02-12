---
layout:     post
title:      "Refactoring by Martin Fowler Part 6"
date:       2018-02-09 08:38:00
summary:    "A catalog of refactorings." 
categories: refactoring
---

**Split temporary variable**  
* What: Temporary variable assigned more than once.  
* Fix: Make a separate variable for each assignment.  
* Why: The fact that they are set more than once means they have more than one responsibility. Confusing for the reader.  

**Replace Method with Method Object**  
* What: Long method that uses local variables in a way that you can't extract out methods.  
* Fix: Turn method into an object with the local variables as fields.
 

