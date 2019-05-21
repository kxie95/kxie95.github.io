---
layout: post
title: "Angular Notes"
date: 2019-05-08 08:38:00
summary: "Learning the fundamentals for my work which uses Angular 7."
categories: frontend frameworks angular
---

# How an Angular app gets loaded
- Our single page: `index.html` -> Refers to a component, say `<app-root>`
- Component defined using decorator `@Component` in a ts file, which specifies the name, its template and css.
- `main.ts` is the first code that gets loaded using `bootstrapModule()`.
- `app.module.ts` tells angular about which components it should know about. In the `bootstrap` property it contains the component AppRoot.

# Directives
- **Attribute directives**: Normal HTML attribute, only affects that element they are added to.
- **Structural directives**: Noraml HTML attribute with a leading *. Removes/adds DOM elements.   