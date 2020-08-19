---
layout: post
title: "How to explain things"
date: 2020-05-18 09:00:00
summary: "Have you ever had a dream that you, um, you had, your, you- you could, you’ll do, you- you wants, you, you could do so, you- you’ll do, you could- you, you want, you want them to do you so much you could do anything?"
categories: javascript eventloop advanced
---

# Javascript advanced concepts
Notes taken from https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop.

## Concurrency model and the event loop
![Javascript runtime]({{ site.url }}/images/javascript-runtime-diagram.svg)

### Stack
Each function call forms a **frame**. 

### Heap
Large region of memory where objects are allocated.

### Queue
List of messages to be processed.

Each message has an associated function which gets called to handle the message.

### How it all works together
During the event loop, the runtime starts handling the messages on the queue (FIFO).
1. Message is removed from the queue
2. Its corresponding function is called with the message as an input parameter
3. Function creates new stack frame
4. Continues until the stack is empty.
5. Process next message in queue.

These steps continue in a loop.

### Event loop
```javascript
while (queue.waitForMessage()) {
  queue.processNextMessage()
}
```
This is more or less how the event loop works.

`queue.waitForMessage()` waits **synchronously** for a message to arrive. 

#### The event loop never blocks. 
Handling I/O is performed via events and callbacks, so it can still process things like user input while waiting for an XHR request to return for example.
