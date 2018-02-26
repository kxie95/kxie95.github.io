---
layout:     post
title:      "4 Rules of Simple Design"
date:       2018-01-27 07:57:00
summary:    "Four rules which help drive simplicity in design, no matter which programming language you work with." 
categories: simple design
---

## Tests pass  
Write tests which verify the behaviour of your code.  

**How**  
I strongly prefer to do this TDD Red-Green-Refactor style when possible.  
* Write a test
* Make it pass
* Refactor

**Why**  
* Ensures your software works as intended. No production code should ever be pushed out without verifying that it works.
* Make you the user of your own code and therefore makes you reflect on the design of it.

## Reveals intent  
Your code should communicate its intention/purpose to another person.  

**How**  
* Naming of variables, methods and classes should be meaningful. (Read Clean Code - Naming)
* Layout your code in logical blocks (line breaks to separate out chunks of logic, tabbing, etc). 

**Why?**  
* Software is for humans first, and computers second.
* You are not going to be the only one working on the piece of code you write.

> There are only two hard things in Computer Science: cache invalidation and naming things. - Phil Karlton  

## No duplication
Don't repeat yourself - do not write two pieces of code which do the same thing. This means duplication of intent, not necessarily code. Most of the time if you are duplicating code though it's very likely you are duplicating intent.  

**How**  
* Every time you finish making a test pass, look at your code to see if there are places which do the same thing. Refactor it.
* Have a clear, logical code structure so other people don't repeat work you've already done.
* Code reviews.

**Why**  
* Creates waste in your code base.
* Whenever you make a change to that behaviour, it means you have to update all instances of it.
* Or even worse, you forget to update it (had this happen in my team recently).

## Small
Solution should be concise - anything that doesn't follow the other 3 rules should be removed.  

**How**  
* Write the smallest amount of code to make the tests pass.
* Might mean considering different algorithms, but this is often not the case.  

**Why**  
* Writing less code is better - it means there are fewer places where things can go wrong.
* Faster to understand, if you follow the other 3 rules.
    
# Order of priorities  
Martin Fowler shows the order of priorities of these rules.  

![Order of priorities](https://martinfowler.com/bliki/images/beckDesignRules/sketch.png "Source: https://martinfowler.com/bliki/BeckDesignRules.html")