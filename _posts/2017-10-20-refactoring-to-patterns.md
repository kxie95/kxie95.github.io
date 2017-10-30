---
layout:     post
title:      "Refactoring to Patterns: Intro & Chapter 2"
date:       2017-10-26 08:03:00
summary:    "" 
categories: refactoring patterns book
---

### Intro
* Lots of wisdom in studying the evolution of a software system rather than its end state.
* Patterns are where you want to be, refactorings are ways to get there. - Martin Fowler  
My comments:  
* I don't see a lot of patterns in our code base. Am I just not recognising them or are patterns not used much?
* I learned about patterns at university but hardly ever applied any. Only one I used was Singleton and that tends to be abused. 

### Refactoring
* Behaviour preserving
* Business priorities and refactoring must be balanced  
Why refactor?
* Easier to add code
* Improve the design
* Gain better understanding
* Make code less annnoying  
Need many eyes to make things better.  

Design debt occurs when you don't consistently:
1. Remove duplication
2. Simplify your code
3. Clarify your code's intent  

### Composite and Test-Driven Refactorings
* **Composite refactorings** are high-level refacorings composed of low-level refactorings
* **Low-level refactorings**: Extract Method, Pull Up Method to superclass, Extract Class, Move method to another class. You must/should run tests.
* **Test-driven refactoring**: Applying TDD to produce replacement code then swap out old code for new code. Old tests and rerun. Helps you produce new design safely.
* Good to use test-driven refactoring when numerous classes need to be updated.  

### Benefits of Composite Refactorings
* Describes a safer refactoring sequence to take.
* Suggests non-obvious design directions.
* Provide insights into implementing patterns.