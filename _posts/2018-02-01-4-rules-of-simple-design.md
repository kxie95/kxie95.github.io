---
layout:     post
title:      "4 Rules of Simple Design"
date:       2018-01-25 07:16:00
summary:    "Four rules which help drive simplicity in design, no matter which programming language you work with." 
categories: simple design
---

**Tests pass**  
* What: Write tests which verify the behaviour of your code. Ideally do this TDD style.
* Why: Makes sure that the software works as intended. No production code should ever be pushed out without verifying that it works.  

**Reveals intent**  
* What: Your code should communicate its intention to another person.
* Make sure naming of variables, methods and classes are meaningful. (Read Clean Code - Naming)
* Good layout of code (line breaks where it makes sense, tabbing, etc). 

Naming example  
```csharp
public double convertPay(string str) {
    return double.Parse(str);
}
```  
```csharp
public double convertPay(string pay) {
    return double.Parse(pay);
}
```  

**No duplication**
* What: Don't repeat yourself - do not write two pieces of code which do the same thing.
* This means duplication of intent, not necessarily code.
* Most of the time if you are duplicating code though it's very likely you are duplicating intent.
* Why: You create waste and this introduces a danger of forgetting to update functionality in multiple places.  

**Small**
* What: Solution should be concise - anything that doesn't follow the other 3 rules should be removed.
* Why: Writing less code is better - fewer places where things can go wrong and faster to understand (usually).
* Write the smallest amount of code to make the tests pass.  
  
  
Order of priorities  
![Order of priorities](https://martinfowler.com/bliki/images/beckDesignRules/sketch.png "Source: https://martinfowler.com/bliki/BeckDesignRules.html")