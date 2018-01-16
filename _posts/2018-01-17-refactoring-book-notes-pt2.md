---
layout:     post
title:      "Refactoring by Martin Fowler notes - Part 2"
date:       2017-12-22 07:16:00
summary:    "Problems, Design and Performance." 
categories: refactoring martin fowler
---

## Problems with refactoring

### Databases
* Most apps tightly coupled to the database schema.
* Data migrations.
* Can make a layer between object model and database if object model becomes to volatile.

### Changing Interfaces
