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

**Introduce Null Object**  
* What: You have a bunch of null checks everywhere.
* Fix: Replace null value with a null object, or implement a null interface.  
* Why: Instead of checking for nulls, you can simply invoke the behaviour without checking for it.
*My thoughts: Is this really preferable to checking for nulls? A null class seems just as noisy, but I suppose then it's all in one place instead of scattered everywhere.*  

**Introduce Assertion**  
* What: A section of code assumes something about the state of the program.
* Fix: Make the assumption explicit with an assertion.  
```java
double getExpenseLimit() {
    // should have either expense limit or a primary object
    return (_expenseLimit != NULL_EXPENSE) ? _expenseLimit : _primaryObject.getMemberExpenseLimit();
}
```  

```java
double getExpenseLimit() {
    Assert.IsTrue(_expenseLimit != NULL_EXPENSE || _primaryObject != null);
    return (_expenseLimit != NULL_EXPENSE) ? _expenseLimit : _primaryObject.getMemberExpenseLimit();
}
```