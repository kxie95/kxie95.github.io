---
layout:     post
title:      "Refactoring to Patterns Ch 4: Code smells"
date:       2017-11-05 17:52:00
summary:    "" 
categories: refactoring code smells
---

### Most common design problems result from code that is:
* Duplicated
* Unclear
* Complicated  

## Common smells and techniques to apply
Depends on the context - need to look into each pattern.  

### Duplicated code
* Form template method
* Polymorphic creation with factory method
* Chain constructors
* Replace one/many distinctions with composite
* Unify interfaces with adapter
* Introduce Null Object

### Long methods
Short methods are better than long ones - if you break long methods into shorter ones it's easier to identify shared logic.  
* Compose method
* Move accumulation to collecting parameter  

Rest of chapter is too long and is a summary of patterns you can use to counter code smells.