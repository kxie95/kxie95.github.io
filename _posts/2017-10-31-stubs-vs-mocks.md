---
layout:     post
title:      "Stubs, Spies & Mocks"
date:       2017-10-31 16:40:00
summary:    "" 
categories: testdoubles stubs mocks spies
---

[Martin Fowler's Blog used as reference](https://martinfowler.com/articles/mocksArentStubs.html)  

These are all test doubles; an test object used to mimic a real object.  

### Stubs
* Completely dumb; no logic.
* Only knows how to return responses for calls.
* Have pre-defined responses for calls that are made to them - they will not respond to anything else.  

### Spies
* Are stubs that record information based on how they were called.  

### Mocks
* Object set up with pre-defined return values to its method calls.
* Used to verify behaviour by using pre-programmed expectations.  

