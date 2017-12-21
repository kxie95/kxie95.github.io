---
layout:     post
title:      "React Redux"
date:       2017-12-19 09:27:00
summary:    "" 
categories: redux react
---

## Principles of Redux
* **State** is readonly
* **Actions** describe what is changing in the application
* **Reducers** - Takes state of whole app and action returns the next state. Must be pure (no side effects and doesn't modify the parameters it takes in).  

## In practice

* Actions are assigned to the store. View dispatches action.
* Store holds the current state.
* View subscribes to Store to get the new state.  

Below is more or less what `createStore` does in Redux.  
```javascript
const createStore = (reducer) => {
    let state;
    let listeners = [];

    const getState = () => state;

    const dispatch = (action) => {
        state = reducer(state, action);
        listeners.forEach(listener => listener());
    };

    const subscribe = (listener) => {
        listeners.push(listener);
        return () => {
            listeners = listeners.filter(l => l != listener);
        };
    };

    dispatch({});

    return { getState, dispatch, subscribe };
} 
```