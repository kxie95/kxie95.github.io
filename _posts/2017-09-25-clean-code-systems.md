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
* Convention over configuration - eg. entity details contained within annotations.

#### Test Drive the System Architecture
* Can make radical change if the structure of the software separates its conerns effectively.
* Have expectations of the general scope, goals and schedule and general structure of the resulting system.
* Summary: An optimal system architecture consists of **modularised domains of concern**, each of which is implemented with POJOs or objects which aren't tied to a particular framework or implementation. The different domains are **integrated together with minimally invasive Aspects** or Aspect-like tools. This **architecture can be test-driven**, just like the code.

#### Optimise decision making
* Postpone decisions until the last possible moment.

#### Use standards wisely, when they add demonstrable value
* Standards make it easier to: reuse ideas, recruit people, encapsulate good ideas and wire components together.
* Standards make it hard to: move fast at times and can lose touch with the real needs of the adopters they are intended to serve.

#### Systems need domain-specific languages
* DSLs allow all levels of abstruaction and all domains in the application to be expressed as POJOs, from high-level policy to low-level details.  

**TLDR: Intent should be clear at all levels of abstraction. Never forget to use the simplest thing that can possibly work.
