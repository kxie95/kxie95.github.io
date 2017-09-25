---
layout:     post
title:      "Clean Code: Systems"
date:       2017-09-25 19:13:00
summary:    "" 
categories: clean code systems
---

#### Separate constructing a system from using it
* Construction is a very different process from use
* Code for startup is usually ad-hoc and mixed in with runtime logic - BAD!

#### Separation of Main
* Move all aspects of construction to main, and design the rest of the system under the assumption that these have **already been constructed**.

#### Factories
* Can use the *abstract factory pattern* to give the application control of **when to build objects**, but keeps the details of that construction **separate from the application code.**

#### Dependency Injection
* Secondary responsibilities are moved to other objects that are dedicated to the purpose.
* These other objects are usually the **main** routine or a special-purpose **container**.

#### Scaling Up
* We never get systems right the first time.

#### Cross-cutting concerns
* Concerns which are needed throughout the application, such as logging, security and persistence.
![_config.yml]({{ site.baseurl }}/images/cross-cutting-concerns.PNG)
* Convention over configuration - eg. entity details contained within annotations.