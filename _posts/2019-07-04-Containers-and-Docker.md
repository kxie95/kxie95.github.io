---
layout:     post
title:      "Containers and Docker"
date:       2018-07-04 07:32:00
summary:    "Attempting to explain what Containers and Docker are to myself."
categories: readings 5voices 
---

## Containers
__Taken from Docker__:  
A container image is a lightweight, stand-alone, executable package of a piece of software that includes everything needed to run it: code, runtime, system tools, system libraries, settings. Containers isolate software from its surroundings, so reduces conflicts running different software on the same infrastructure.  

__My take__:  
A container image is an executable which includes all the dependencies it needs to run it.  

So some examples may be that sometimes you download software and it tells you "You need Java 8 for this!" - containers solve that problem by packaging Java 8 in the container so it can just run. Another example is if, say, you're testing with Python 2.7 but then the code runs in Python 3 when deployed, things will likely go wrong.

## What is Docker
__Taken from Wikipedia__:  
Docker is a computer program that performs operating-system-level virtualization also known as containerization.  

__My take__:  
Docker is the program which makes it possible to run different containers on the same machine. People always compare containerization to virtualization, and I now understand why. Docker is like the hypervisor to virtual machines.  
  
With virtual machines, the hypervisor separates the hardware from the operating system and applications. With containers, Docker separates the host operating system and hardware from the application and its libraries. [Insert image to illustrate].
