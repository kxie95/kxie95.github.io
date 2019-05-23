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

- When creating attribtue directives you should use `[]` around the name of the selector.
- When accessing the DOM, you should use the Renderer class because Angular can run in other environments where there might not be a DOM (eg. Service Workers).
- You can use HostListeners/HostBinders to listen to mouse events or bind the the elements properties.
- You can pass custom values to directives using `Input()`.

# Services
Injector Heirarchy
- Propogates downwards.
- AppModule - same instance will be available application-wide.
- AppComponent - same instance available for all Components (but not for other Services)
- Any other Component - same instance available for the Component and its children 

@Injectable
- Use this when you want to inject a service into another service

# Routing
- With traditional routing (with anchor link), the whole page reloads when you redirect to a different path.
- With Angular Router, you use a special directive `routerLink` so that it can capture the path, prevent the page from reloading and load the component from registered routes.
