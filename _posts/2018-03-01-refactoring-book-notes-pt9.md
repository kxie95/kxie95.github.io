---
layout:     post
title:      "Refactoring by Martin Fowler Part 9"
date:       2018-03-01 07:45:00
summary:    "Dealing with generalisation" 
categories: refactoring
---

Many of the sections in "Dealing with Generalisation" are heavily focussed on fixing inheritance hierarchies. This is pretty straightforward - like making common fields up into a superclass, pushing fields down which are specific to one class, etc. I decided to omit these from my notes.  

**Extract interface**  
* Several clients use the same subset of a class's interface, or two classes have part of their interfaces in common.
* Extract the subset into an interface.
* Particularly useful when a class needs to work with any class that can handle certain requests. Good to use whenever a class has distinct roles in different situations.

**Form Template Method**  
* You have two methods in subclasses that perform similar steps in the same order, yet the steps are different.
* Get the steps into methods with the same signature, so that the original methods become the same. Then you can pull them up.

Example - Before  

```java
class ResidentialSite {
    public void getBillableAmount() {
        double base = _units * 5;
        double tax = _taxRate * 12;
        return base + tax;
    }
}

class LifelineSite {
    public void getBillableAmount() {
        double base = _units * 2 * _rate;
        double tax = _taxRate * 9 * base;
        return base + tax;
    }
}
```  

Example - After - Superclass contains the template method, subclasses implement `getBaseRate()` and `getTaxRate()`.    

```java
class Site {
    public void getBillableAmount() {
        return getBaseRate() + getTaxRate();
    }
}
```  

**Replace inheritance with delegation**  
* A subclass uses only part of a superclass's interface or does not want to inherit data.
* Create a field for the superclass, adjust methods to delegate to the superclass, and remove the subclassing.
* The problem with inheritance is that you inherit a bunch of things you probably don't need. Makes more sense to delegate instead.

Example: MyStack originally called its inherited superclass methods but was changed to call these from its private field instead.  
We can then break the link to the superclass and add extra methods as needed without having to inherit everything from `Vector`.  

```java
class MyStack extends Vector {
    private Vector _vector = this;
    
    public void push(Object element) {
        _vector.insertElementAt(element, 0);
    }

    public void pop() {
        Object result = _vector.firstElement();
        _vector.removeElementAt(0);
        return result;
    }
}
```
