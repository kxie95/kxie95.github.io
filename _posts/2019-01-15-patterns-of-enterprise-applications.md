---
layout: post
title: "Patterns of Enterprise Application Architecture: Notes"
date: 2019-01-15 08:27:00
summary: ""
categories: architecture enterprise
---

This book seems like a catalogue of common architectural patterns that Martin has encountered in his career. He says that the list is not exhaustive, as his knowledge continues to evolve even as he wrote the book.

I'm not actually sure how useful this book is for me at this point in my career, but I find myself not being able to contribute much to design discussions. I thought this would be a good starting point along with a book about design patterns.

As with all patterns, I understand that they are starting points for discussions, not a cookie-cutter solutions for problems I'm given. They might evolve how I think about a particular problem though, so that's why I'm giving this book a go :)

## Layers

- 🍰 :)
- Making sure layers below are unaware of the layers above.
- Useful because you can swap out a given layer without affecting layers above.
- Performance overhead if too many layers, but organisation benefits usually outweigh performance.
