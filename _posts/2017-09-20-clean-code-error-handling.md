---
layout:     post
title:      "Clean Code: Error Handling"
date:       2017-09-20 07:16:00
summary:    How we should be doing error handling. 
categories: clean code error handling
---

Use exceptions.  

#### Checked exceptions
* Violation of the Open Closed Principle.
* If you have a throws exception at the bottom level, this cascades all the way up.  

#### Provide context with exceptions
* Should be able to determine source and location of an error.
* Create informative error messages.  

#### Define exception classes in terms of caller's needs
* Sometimes just use a common exception.
* Wrap your APIs and define one you are comfortable with.  

#### Define the normal flow
* Special Case Pattern - create a class so that it handles a special case for you.  

### Don't return null
* This will make your whole application check for nulls.
* Throw an exception or return a special case object instead.
