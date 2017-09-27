---
layout:     post
title:      "Clean Code: Four Rules of Simple Design"
date:       2017-09-28 08:16:00
summary:    "" 
categories: clean code emergence four rules simple design
---

### Four rules of simple design
#### Runs all tests
* A design must prodice a system that acts as intended.
* To verify this, we must be able to test the system. A system which cannot be verified should not be deployed.
* Making our systems testable pushes us toward a design where our classes are small and have a single purpose.
* Tight coupling makes it difficult the write tests. The more tests we write, the more we use principles like DIP, interfaces and abstraction to minimise coupling.  

#### Refactoring
* For each few lines of code added, ask: "Did we just degrade it?"
* This is also where we also apply the other rules of simple design.  

#### No duplication
* Can exist as code that looks exactly alike, or duplication of intent.
* Achieving reuse in the small is essential to achieving reuse in the large.

#### Expressive
* It's easy to understand your code at the time because you're so deep the problem. The future you/someone else is not going to know.
* Use good names, keep your functions and classes small.
* Can also use standard nomenclature. eg. Design patterns <-- Not too sure about this one.
* Well written unit tests.
* **Take care and take pride in your workmanship**  

##### Minimal classes and methods
* SRP can be taken too far (too many tiny classes), so this rule suggests that we also keep our function and class counts low.
* Consider a coding standard that insists on creating an interface for each and every class or fields and behaviours must always be separated into data classes and behaviour classes. **NO!!!**
* Goal is to keep overall system small while also keeping functions and classes small.