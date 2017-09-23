---
layout:     post
title:      "Clean Code: Unit Tests"
date:       2017-09-21 08:16:00
summary:    "" 
categories: clean code unit tests
---

#### 3 Laws of TDD
* You may not write production code until you have written a failing test.
* You may not write more of a unit test than is sufficient to fail, and not compiling is failing.
* You may not write more production code than is sufficient to pass the current failing test.

#### Keeping tests clean
* Dirty tests = no tests
* Tests are just as important as production code
* **Tests enable change**: Tests verify that what you have done does not break existing code.
* **Clean tests** are readable: They are clear, simple and say a lot with few expressions.
* Refactor your test code!

#### Guidelines for writing unit tests
* One assert per test/reduce the number of asserts per test
* Single concept per test
* **F.I.R.S.T** - Fast, Independent, Repeatable, Self-validating, Timely.  

Take care of your test code or your production code will rot!
