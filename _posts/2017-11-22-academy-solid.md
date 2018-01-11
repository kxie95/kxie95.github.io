---
layout:     post
title:      "SOLID"
date:       2017-11-22 08:24:00
summary:    "" 
categories: academy solid
---

## Single Responsibility Principle
**A software module should have one and only one reason to change.**  
We want cohesion between things that change for the same reason, and we want to decrease the coupling between those things that change for different reasons.  

Here is an example of something that breaks the SRP:
```
public class Game() {
    public void Start();
    public void End();
    public void CheckWin();
    public void ValidateMove();
}
```
This example breaks the SRP because `Game` is doing too many things. A game should only be concerned with starting, ending and making moves. I would move those methods out into classes concerned wtih validation and checking state.

## Open-closed principle
**A software module should be open for extension and closed for modification.**  
Functionality should be added to a module without having to modify the internal workings of it. By applying this principle, less work is required to adjust for new functionality to the code, and will make it safer to add new functionality too. 

Here is an example of code that breaks the OCP:  
```
public void DoActionForKeyPress(string key) {
    switch (key) {
        case "k":
            doKAction();
        case "i":
            doIAction();
    }
}
```
If we wanted to add a new action for a key press, we would have to add an extra case statement. We are modifying the inner workings of the method.  

The following code shows one way to fix this:
```
Dict<string, Action> _keyActions;

public void DoActionForKeyPress(string key) {
    _keyActions[key]();
}
```
We introduce a field which is injected into the class. With this new implementation, everytime we need a new action for a key press we simply provide it ourselves, rather than having to add new code inside the method everytime. The modification of behaviour is now outside of the method (hence the method is closed for modification).

## Liskov Substitution Principle
**A class can be substituted with any of its subclasses and not break anything.**  
This principle is all about forming the correct abstractions.  

For example:
```
public class Book() {
    public void TurnPage();
}
public class TextBook extends Book() {...}
public class KindleBook extends Book() {...} 
```
`KindleBook` can turn pages, but won't function unless it has at least 1% battery. So if we were to substitute a call to `Book.TurnPage()` with `KindleBook.TurnPage()` somewhere in the code, ignoring the fact that we need power, this could break the code.

### Interface Segregation Principle
**To be continued**  

#### References:
[Single Responsibility Principle by 8th Light](https://8thlight.com/blog/uncle-bob/2014/05/08/SingleReponsibilityPrinciple.html)