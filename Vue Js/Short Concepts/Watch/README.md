# Vue Watch: A Beginner’s Guide

This document covers Vue's watch functionality, explaining key concepts in its usage.

## Table of Contents

1. Syntax
2. How watch Works
3. Deep Watching
4. Multiple Dependencies
5. Summary

## 1. Syntax

The basic syntax of watch is:

```js
watch(x, callback);
```

Where:

- **x**: This is the reactive variable you want to observe.
- **callback**: This function executes when x changes, receiving the new value of x (and optionally, the old value) as parameters. 

## 2. How watch Works

### A Practical Example
Suppose you want to store a user's name in localStorage every time it changes. Here’s how you’d do it with watch:

```js
watch(name, (newName) => {
localStorage.setItem('name', newName)
})
```

Here:

1. The `watch` function is observing the variable `name`.
2. Whenever `name` changes, Vue calls the callback function with `newName` (the updated value of name).
3. Inside the callback, `newName` is stored in localStorage.
### Vue’s Behind-the-Scenes Assignment
In Vue, `watch` automatically assigns the updated value of name to newName. This means that whenever name changes, Vue passes this new value as `newName` to the callback function. This automatic assignment allows you to work with the most current value without additional code.

## 3. Deep Watching
Sometimes, you need to watch **`nested data structures`** (like objects or arrays). By default, watch only detects changes at the top level. Use `{ deep: true }` for a “deep watch”:

```js
watch(dataObject, (newVal) => {
console.log('Data object changed:', newVal);
}, { deep: true });
```
With deep: true, Vue tracks changes to nested properties within `dataObject`.

## 4. Multiple Dependencies
You can observe multiple values by passing an array of dependencies. Each dependency is updated independently, so when one changes, the callback triggers with the latest values:

```js
watch([data1, data2], ([newData1, newData2]) => {
console.log('data1 or data2 changed');
});
```

In this example, if either `data1` or `data2` changes, Vue calls the callback with their new values.

## 5. Summary
- watch is used to react to changes in reactive data.
-   Vue automatically assigns the updated value of the observed variable to the callback parameter.
-    `{ deep: true }` option enables deep tracking for nested data structures.
-    **Multiple dependencies** can be observed by passing an array.
