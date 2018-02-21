---
layout:     post
title:      "Refactoring by Martin Fowler Part 7"
date:       2018-02-22 07:58:00
summary:    "A catalog of refactorings - Simplifying Conditionals" 
categories: refactoring
---

**Replace Nested Conditional with Guard Clauses**  
* What: A method has conditional behavious that does not make clear the normal path of execution.
* Fix: Use guard clauses for all the special cases.
```java
double getPayAmount() {
    double result;
    if (_isDead) {
        result = deadAmount();
    } else {
        if (_isSeparated) {
            result = separatedAmount();
        } else {
            if (_isRetired) {
                result = retiredAmount();
            } else {
                result = normalPayAmount();
            }
        }
    }
    return result;   
}
```  

```java
double getPayAmount() {
    if (_isDead) return deadAmount();
    if (_isSeparated) return separatedAmount();
    if (_isRetired) return retiredAmount();
    return normalPayAmount();
}
```
 

