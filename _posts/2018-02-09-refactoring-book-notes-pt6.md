---
layout:     post
title:      "Refactoring by Martin Fowler Part 6"
date:       2018-02-09 08:38:00
summary:    "A catalog of refactorings." 
categories: refactoring
---

**Split temporary veriable**
What: Temporary variable assigned more than once.  
Fix: Make a separate variable for each assignment.  
Why: The fact that they are set more than once means they have more than one responsibility. Confusing for the reader.  

