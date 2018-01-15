---
layout:     post
title:      "Refactoring my ugly minesweeper kata"
date:       2018-01-09 08:34:00
summary:    "" 
categories: refactoring minesweeper
---

[See my solution here.](https://github.com/xiekaren/minesweeperkata/tree/refactor)  

`master` currently has my unrefactored solution which uses a `dictionary` (bad idea by the way!).    
`refactor` has the refactored version of my solution - I will be cleaning up and trying to take a more functional approach.  

## The journey
This solution is relatively well-tested, enough that it will pick up changes if the output is slightly wrong.  

**Let's start at `Minesweeper.cs`. I start by extracting out bits of functionality to make the solution more readable.**  
* Scratch this way of doing things - although it is more efficient (but probably negligible), it makes things harder to read.   

**Decided to process input altogether.**   
* Transform into list of `Field` objects -> create hints -> print out list.
* Instead of: transforming, creating hints then printing out for each field in the input.
* Wrote top level test for transforming the input into a `Field` list. Make them pass, refactor. Make `Location` class to represent single point.
* Wrote top level test for transforming `Field` list into `FieldHints`. Make them pass, refactor.  

**Went through and deleted all the old classes.**  
* Use `Find references` to be safe before deleting.  

**Lots of pulling out fat methods and eventually converting them to new classes.**   

**Created an `IFormatter` interface for my formatters.**  