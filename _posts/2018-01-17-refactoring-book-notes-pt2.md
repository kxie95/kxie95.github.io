---
layout:     post
title:      "Refactoring by Martin Fowler notes - Part 2"
date:       2018-01-22 07:16:00
summary:    "Problems, Design and Performance." 
categories: refactoring martin fowler
---

## Problems with refactoring

### Databases
* Most apps tightly coupled to the database schema.
* Data migrations.
* Can make a layer between object model and database if object model becomes to volatile.

### Changing Interfaces
* Only a problem if you have a published interface.
* Can make your old interface call your new interface.

### Design changes are difficult to refactor
* Eg. A system that hasn't been built with security in mind.
* May need to imagine up a new design and see how hard it is to reach.

### When you shouldn't refactor
* Code has to work mostly correctly before you refactor. If it doesn't, you might just have to rewrite.
* When you're too close to the deadline.
