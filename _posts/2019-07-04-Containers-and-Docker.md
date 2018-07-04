---
layout:     post
title:      "Containers, Docker, and related concepts"
date:       2018-07-04 07:32:00
summary:    "Attempting to explain what Containers and Docker are to myself."
categories: readings 5voices 
---

I've used Docker for about 6 months now, and these are the terms I got confused with while learning it. I think it's important to understand these concepts when working with Docker or you will have no idea what is actually happening.  

## Basic Concepts
### Containers
__From Docker__:  
A container image is a lightweight, stand-alone, executable package of a piece of software that includes everything needed to run it: code, runtime, system tools, system libraries, settings. Containers isolate software from its surroundings, so reduces conflicts running different software on the same infrastructure.  

__My take__:  
A container image is an executable which includes all the dependencies it needs to run it.  

So some examples where I think this is useful:  
* Sometimes you download software and it tells you "You need Java 8 for this!" - containers solve that problem by packaging Java 8 in the container so it can just run.
* Another example is if, say, you're testing with Python 2.7 but then the code runs in Python 3 when deployed, things will likely go wrong.

In the above samples, software is dependent on what's installed in a given environment or machine. So if you can eliminate that dependency, fewer things can go wrong!

### Images, Layers and Containers
__Images__: Are like the stencil for making a container. You can stack __layers__ on top of an image. Images are __read-only__, so you can't change what's on them.  

__Layers__: Are intermediate images generated from other images. So you can start off with a python image, and then add, for example, an "install wget layer". So the image now has python and wget. When you build this image, that's what the container will have. Like images, layers are read-only, so once created they can't be modified.

__Containers__: Are like the objects you make from a stencil. They are __instances__ of an image.
  
[Add illustration]

## Docker Specifics
### What is Docker
__From Wikipedia__:  
Docker is a computer program that performs operating-system-level virtualization also known as containerization.  

__My take__:  
Docker is the program which makes it possible to run different containers on the same machine. People always compare containerization to virtualization, and I now understand why. Docker is like the hypervisor to virtual machines.  
  
With virtual machines, the hypervisor separates the hardware from the operating system and applications. With containers, Docker separates the host operating system and hardware from the application and its libraries. [Insert image to illustrate].  

### Dockerfile
A Dockerfile is where you can stack layers on top of an image. Each command creates a new layer. When you `docker build`, you can see these layers being generated with their IDs. The output is an image:  

```
$ docker build -t expressweb .
Step 1 : FROM node:argon
argon: Pulling from library/node...
...
Status: Downloaded newer image for node:argon
 ---> 530c750a346e
Step 2 : RUN mkdir -p /usr/src/app
 ---> Running in 5090fde23e44
 ---> 7184cc184ef8
Removing intermediate container 5090fde23e44
Step 3 : WORKDIR /usr/src/app
 ---> Running in 2987746b5fba
 ---> 86c81d89b023
Removing intermediate container 2987746b5fba
Step 4 : COPY package.json /usr/src/app/
 ---> 334d93a151ee
Removing intermediate container a678c817e467
Step 5 : CMD npm start
 ---> Running in a262fd016da6
 ---> fdd93d9c2c60
Removing intermediate container a262fd016da6
Successfully built fdd93d9c2c60
```  

When you then do a `docker run`, that's when a container is made from the image you built.

