---
layout: post
title: "Cohesion and Coupling"
date: 2019-05-22 15:01:00
summary: ""
categories: cohesion coupling
---

## What is cohesion?
**Cohesion** refers to a whether a entity has a well-defined purpose, doing as little as possible. Entities which have a well-defined purpose have **high cohesion**, and those that don't have **low cohesion**.

Example: Low cohesion
```csharp
class Helpers {
    public string FormatString(string unformatted) { ... }
    public void RemoveHeader(Header header) { ... }
    public int GetValueFromRequest(Request request) { ... }
}
```
Many code bases and myself are guilty of dumping certain functions together in a class called `Helpers` which are "reusable". `Helpers` is a very generic term which already breaks our definition of having a well-defined purpose, doing as little as possible.

Indicators of low cohesion:
- When you change something, changes need to be made in many places.
- Many methods which don't act together within a class.

Example: High cohesion
```csharp
class Account {
    private double _balance;
    public void Deposit(double amount) { _balance += amount; }
    public void Withdraw(double amount) { _balance -= amount; }
}
```
It's clear looking at this entity that the purpose is to keep track of the balance for an account. The methods work together to act on the balance, which makes this class cohesive.

These are just some examples. There are gradients of cohesion:
1. Coicidental (lowest)
2. Logical
3. Temporal
4. Procedural
5. Communicational
6. Sequential
7. Functional (highest)

## What is coupling?
**Coupling** refers to how much two entities depend on each other.
We refer to entities which depend on each other a lot as **tightly coupled**, and entities which are opposite are **loosely coupled**.

Types of coupling:
- Content: When one entity modifies or relies on the internal workings of another entity.
- Common: When several entities have access to the same global data.
- Stamp: When an entity passes more information than needed to another entity.
- Control: Passing a flag to tell a method what to do. Now calling clients know there is an if inside.
- Data: Passing parameters to a method that doesn't affect its control flow. This type is common and is not necessarily bad.

## References
- https://thoughtbot.com/blog/types-of-coupling