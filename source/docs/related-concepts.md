---
title: "Related Concepts"
description: "Relationship to other projects and architecture features"
---

## Cordova, Electron, CrossWalk, XWebView, NW, etc.

Actually, we've built upon the shoulders of all of these and similarly on the excellent Nodelike and Nodyn projects (both no longer maintained) and even Microsoft's Node fork for ChakraCore, by taking the approach of re-writing the bindings to V8.  However, we've written or re-used as much code in JavaScript as far as possible.  The whole theory of the Node ecosystem is that JavaScript is pretty fast, in fact when compiled like we can with the Nitro engine used by {NK} NodeKit its really really fast.  Bridging back and forth to native tends to introduce latency which we like to avoid except where essential or where done for us by the emerging HTML5 / ES5 /ES6 features of most modern JavaScript engines.

The real motivation for us however, wasn't speed of execution, but rather we didnt want to include a large 48Mb executable for Chromium or its javascript engines in every app download... when most modern operating systems already include an ES5 engine.
