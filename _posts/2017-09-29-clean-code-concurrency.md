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