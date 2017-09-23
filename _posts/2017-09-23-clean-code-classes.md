---
layout:     post
title:      "Clean Code: Classes"
date:       2017-09-23 14:46:00
summary:    "" 
categories: clean code classes
---

* Classes should be small
* You should be able to write a brief description of the class without using the words "if", "and", "but" and "or".  

#### Single Responsibility Principle
* A class should only have one reason to change.
* Trying to identify responsibilities often helps us recognise and create better abstractions for our code.  

#### Cohesion
* Classes should have a small number of instance variables.
* The more variables a method manipulates the more cohesive that method is to its class.
* When there is a proliferation of variables that are used by a subset of methods, this usually means there is a class that can be extracted out.

#### Maintaining cohesion results in many small classes
* Refactor and split a massive class up by writing a test suite that verifies the precise behaviour of the original program.
* Then make little changes one by one.  

#### Organising for change
* TBC