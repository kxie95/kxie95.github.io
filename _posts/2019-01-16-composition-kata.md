---
layout: post
title: "Kata: Composition"
date: 2019-01-16 07:55:00
summary: "My thoughts while reviewing my intern's implementation of the Composition Kata."
categories: katas composition
---

[Link to the kata here](https://github.com/OdeToCode/Katas/tree/master/Composition/CS/Composition)

This kata is not so much about writing clean code/design but more about seeing the pros/cons of inheritance and composition for yourself.

The problem is about implementing different ways of making calculations (summing, averaging, filtering, etc) with code inherited from another programmer that consulted a design patterns book. In the inheritance implementation, they used the template method (which I find funny because we were told to do an exercise for this very pattern in university).

## Inheritance implementation

### Folder structure

```
- AveragingAggregator.cs
- HighPassSummingAggregator.cs
- LowPassAveragingAggregator.cs
- PointsAggregator.cs
- SummingAggregator.cs
```

### Pros & Cons

- **“Pro”**: Reduces the number of lines of code

- **Con**: Every single subclass must implement those exact methods, even if they don’t necessarily need them.

  - Eg. In AveragingAggregator & SummingAggregator even though there was no need to filter measurements you still had to implement it.

- **Con**: Hides functionality
  - Eg. HighPassSummingAggregator & LowPassSummingAggregator - without looking and SummingAggregator, I can’t tell that HighPassSummingAggregator has an AggregateMeasurements() method that adds measurements together.

## Composition implementation

### Folder structure

```
- AveragingStrategy.cs
- EmptyFilter.cs
- HighPassFilter.cs
- HighPassSummingAggregator.cs
- IAggregationStrategy.cs
- IMeasurementFilter.cs
- LowPassFilter.cs
- PointsAggregator.cs
- SummingStrategy.cs
```

### Pros & Cons

- **“Con”**: Looks like there's more code, more files

  - Can easily solve this by organising files into folders

- **Pro**: Flexibility to swap out behavior

  - Interfaces IMeasurementFilter and IAggregationStrategy can easily be swapped out for whatever filter you want. You only need to implement a new filter if you needed to filter, or a new aggregator if you needed to aggregate a different way.
  - With inheritance, you had to create a whole new class, implementing filtering and aggregating together. You’re tied to a specific implementation.

- **Pro**: Each bit of code is very specific about what it does

## The analogy

Inheritance is like using a laptop and buying a new one every time it gets too slow or the screen dies.

Composition is like using a PC and swapping out the CPU/Graphics card when it gets too slow or swapping out the monitor for a new one when the screen dies.
