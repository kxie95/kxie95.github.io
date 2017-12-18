---
layout:     post
title:      "Minesweeper Kata"
date:       2017-12-19 09:27:00
summary:    "" 
categories: minesweeper kata
---
My unrefined solution: [https://github.com/xiekaren/MinesweeperKata](https://github.com/xiekaren/MinesweeperKata)

## After-kata thoughts  
* Thought I did top down by starting at the level where all the fields are parsed into an object representing a minefield.
* Tried using a dictionary to represent the minefield - bad idea because there was no way to order it.
* I can definitely see the benefits in top-down; had I started there I would have thought about the best way to parse the string into the object. As a result my parsing logic is messy.  

## What I would do differently next time  
Now that I've done this I think top-down TDD would look something like this:  
* Write failing test which takes input as a string in the specified format, and expect the output to look like the specified format.
* Write tests and make them pass for parsing the input into a minefield object. 
* Write tests and make them pass for processing the hints for the mines. 
* Write tests and make them pass for outputting this in the correct format.
* Top-down test that you wrote should then pass.  

## What next?
* Probably try out some refactoring techniques onto my not-so-great solution. :)
