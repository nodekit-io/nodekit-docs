---
title: "Getting Started with NodeKit"
description: "This page will help you get started with NodeKit. You'll be up and running in a jiffy!"
---
Try the sample project
```shell
git clone https://github.com/nodekit-io/nodekit-sample.git
cd nodekit-sample
carthage update
```

## iOS and MacOS platforms

Two lines in main.swift to launch an embedded WebKit view and start the NodeKit engine (already included for you in the sample).   

``` swift
import NodeKit
NKNodeKit.start();
```

## Windows platform

Two lines in main.cs to launch an embedded Edge view and start the NodeKit engine (already included for you in the sample).  

``` C#
using io.nodekit
NKNodeKit.start();
```

Then just make sure any standard Node application is in the app/ directory.  This application will run in the `main` process (a hidden but highly performant JavaScript engine such as Nitro WKWebView, JavaScriptCore, Chakra or ChakraCore).   The first thing the application typically does is open a `renderer` window, very similar to Atom Electron: 

``` javascript
const app = require('electro').app;
const BrowserWindow = require('electro').BrowserWindow
app.on('ready', function() {
  var window = new BrowserWindow();
});
```

The sample app includes a built in web server for serving static and dynamic content; on iOS this can be an http server over a localhost port, but on OSX you may want to use no ports at all and just use built in protocol server.

Build in Xcode for both iOS and Mac targets.

Build in Visual Studio or using MBuild for all projects in the solution.
