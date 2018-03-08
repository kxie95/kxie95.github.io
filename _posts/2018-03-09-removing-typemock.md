---
layout:     post
title:      "Removing Typemock"
date:       2018-03-09 07:58:00
summary:    "Pains and learnings from removing Typemock from a project at work." 
categories: refactoring
---

* Typemock allows you to do bad things like mocking private methods.
* Extension methods are a pain because they make it look like that method is a part of that class, when really it's not.
* Extension methods also suck because they are part of a static class which makes them impossible to mock.
* Mocking statics is not supported because mocking libraries usually create mocks by dynamically creating classes at run time which inherit from the class to mock and override behaviour. You can't do this with static classes.