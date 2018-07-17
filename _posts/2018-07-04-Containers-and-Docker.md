---
layout:     post
title:      "Containers, Docker, and related concepts"
date:       2018-07-04 07:32:00
summary:    "Attempting to explain what Containers and Docker are to myself."
categories: readings 5voices 
---

I've used Docker for about 6 months now, and these are the terms I got confused with while learning it. I think it's important to understand these concepts when working with Docker or you will have no idea what is actually happening.  

## Basic Concepts
### Containers as an overall concept
A container is an executable which includes all the dependencies it needs to run it. They isolate software from surroundings. 

So some examples where I think this is useful:  
* Sometimes you download software and it tells you "You need Java 8 for this!".
* Another example is if, say, you're testing with Python 2.7 but then the code runs in Python 3 when deployed, things will likely go wrong.

In the above examples, a piece of software is dependent on what's installed in a given environment or machine. Containers solve this by packaging all the binaries/libraries it needs so that this dependency is eliminated. Because of this, fewer things can go wrong!

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

### The Docker Daemon
The Docker Daemon is a program that runs in the background that allows virtualisation to happen - it does the container management for you. All you need to do is give it commands through your CLI, which sends REST calls to the daemon which then interacts with the Linux Kernel to build and manage containers.  

Interesting to note that containers are possible because of a feature of the Linux Kernel, which allows the creation of an isolated area (limits CPU, memory, network, etc.) in the host.  

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

## Docker compose
Does as the name suggests - composes a bunch of containers. Use this file if you want to spin up multiple containers.

__References__:
* [Docker documentation](https://www.docker.com/enterprise-edition)
* [Digging into docker layers - Jessica G](https://medium.com/@jessgreb01/digging-into-docker-layers-c22f948ed612)
* [Understanding how the Docker daemon and CLI work together](https://nickjanetakis.com/blog/understanding-how-the-docker-daemon-and-docker-cli-work-together)

