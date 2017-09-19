---
layout:     post
title:      Data Structures vs Objects
date:       2017-09-19
summary:    Why does it matter
categories: data structures objects cleancode
---

* Data structures expose their data and have no behaviours.
* Objects expose their behaviours which act on their data which is hidden behind abstractions.
* Hiding implementation is not just about wrapping it in a function. It's about the abstraction. See below.


Interface 1 is just getting its data. Interface 2 is better abstracted; we can't tell what the data looks like.
```
public class Vehicle {
	double getFuelCapacityInGallons();
	double getGallonsOfGasoline();
}
```
```
public class Vehicle {
	double getPercentageFuelRemaining();
}
```

#### Law of Demeter
* Module should not know about the innards of the objects it manipulates.
* Smell: long method chaining.
