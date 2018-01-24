---
layout:     post
title:      "Refactoring by Martin Fowler notes - Part 3"
date:       2018-01-25 07:16:00
summary:    "Problems, Design and Performance." 
categories: refactoring martin fowler
---

## Refactoring and Design

> **"With design I can think very fast, but my thinking is full of little holes."** - Alistair Cockburn  

There are two extreme approaches:  
1. Do every bit of upfront design you can then code.  
2. Don't think about design and refactor it into shape.  

Probably best to find some sort of middle ground.  

With refactoring, the emphasis changes - you don't try to find *the* solution. Instead, you find the most *reasonable* solution until you learn more about the problem. As a result, it is better to focus on **simplicity of design**.  

This is interesting to me because in university, they always stressed building flexible software. Martin points out that that flexibility comes with a cost too. Flexible solutions are more complex than simple ones. Moreover, flexibility isn't really needed most of the time because you can never predict how the requirements of your software will change. Most of the time, **YAGNI**!

With the refactoring approach you think of potential changes and still consider flexible solutions. **Ask yourself: "How difficult is it going to be to refactor a simple solution into the flexible solution?".** Most of the time the answer is "pretty easy".  

