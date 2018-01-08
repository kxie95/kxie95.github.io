---
layout:     post
title:      "Refactoring my ugly minesweeper kata"
date:       2018-01-09 08:34:00
summary:    "" 
categories: refactoring minesweeper
---

[See my solution here.](https://github.com/xiekaren/minesweeperkata)  
`master` currently has my unrefactored solution which uses a `dictionary` (bad idea by the way!).    
`refactor` has the refactored version of my solution - I will be cleaning up and trying to taking a functional approach.  

## The journey
* This solution is relatively well-tested, enough that it will pick up changes if the output is slightly wrong.
* Let's start at `Minesweeper.cs`. I start by extracting out bits of functionality to make the solution more readable.