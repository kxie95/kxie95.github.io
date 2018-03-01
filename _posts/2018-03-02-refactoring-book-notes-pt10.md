---
layout:     post
title:      "Refactoring by Martin Fowler Part 10"
date:       2018-03-02 07:45:00
summary:    "Big refactorings and key takeaways" 
categories: refactoring
---

**Convert Procedural Design to Objects**  
* Take each record type and turn into dumb data objects.
* Take all procedural style code and put it in a single class.
* Take each long procedure and extract out methods + any related refactorings. Move methods into appropriate classes.
* Continue until you've removed all the behaviour away from the original class.  

## Key takeaways
* You know you've become good at refactoring once you're confident that you can make the code better, no matter how screwed up it is.
* Tests are king - have a comprehensive test suite to give you confidence that behaviour hasn't changed and run tests frequently.
* Make the simplest, reasonable solution until you need to make it flexible.