---
layout:     post
title:      "Clean Code: Concurrency"
date:       2017-09-29 07:08:00
summary:    "" 
categories: clean code concurrency
---

### Concurrency defense principles
#### Single responsibility principle
* Keep your concurrency-related code separate from your other code.

#### Limit the scope of data
* Data encapsulation; limit the access of any data that may be shared

#### Use copies of data
* Another way to avoid sharing data. Can make copies and merge results at the end.

#### Threads should be as independent as possible
* Partition data into independent subsets that can be operated on by independent threads.  

### Know your library
* Review that concurrency classes available to you in your language.

### Know your concurrency models
* **Bound resources** - resources of a fixed size or number used in a concurrent environment. eg. Database connections/fixed size read/write buffers.
* **Mutual exclusion** - Only one thread can access shared data or a shared resource at a time.
* **Starvation** - One thread or a group of threads is prohibited from proceeding for an excessively long time/forever. eg. giving priority to the fast running threads might starve out the long running threads.
* **Deadlock** - Two or more threads waiting for each other to finish. Each thread has a resource that the other thread requires and neither can finish until it gets the other resource.
* **Livelock** - Threads in lockstep, each trying to do work but finding another "in the way". Due to resonance, threads continue trying to make progress but are unable for a long time/forever.  

### Execution models in concurrent programming
* Producer-Consumer
* Readers-Writers
* Dining Philosophers
* **TODO**: Learn these algorithms and understand their solutions.

