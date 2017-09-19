---
layout:     post
title:      Javascript Notes
date:       2017-09-19
summary:    Random list of things I learn about Javascript.
categories: javascript notes
---

#### Arrow Functions
* Arrow functions implicitly use `this` as their scope. Therefore there is no need to `func.bind(this)`.
* Likewise, if a function is not an arrow function, they are in their own scope and you will have to use `func.bind(this)`.

#### Promises
* You can chain .then() with functions without specifying parameters - these are automatically passed in.