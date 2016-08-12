---
title: "Motivation"
description: "The problem that NodeKit is trying to solve"
---

## Abstract

NodeKit provides a consistent way of running JavaScript applications on all devices including mobile, desktop, serverless and cloud.

There are some great APIs out there like Node.js and Electron, but unfortunately they only run on servers and desktops respectively.  Further,
 frameworks like Electron require a large download for even the smallest applications since they usually embed a full WebKit rendering and JavaScript engine.

We believe that the JavaScript and webview engine included in most modern operating systems is best served for running these applications.

We believe that providing a consistent API surface like Node.JS enablers developer productivity without having to worry about native implementation 
of networking sockets, cryptography, file systems, etc.

![http://nodekit.io](https://raw.githubusercontent.com/nodekit-io/nodekit/master/docs/images/banner.png?v02)

## Is it really Node ?

*YES* for all the javascript portions (and most of Node is written in javascript, of course).  *NO* for all the V8 bindings.  

We include the direct source files from Node.js source directly in NodeKit (you can find them in the framework package in a folder called lib).  Then we add our own bindings to replace the V8 native ones, writing them in javascript as much as possible, with a few native calls for the really platform specific stuff like sockets, timers, and the file system.  These bindings have exactly the same API signatures as the Node versions so are plugin replacements.

This means most Node packages will work without modification.  Those that require node-gyp native bindings to V8 would require an alternative. 

## JavaScript Engines

So on iOS and Macs we use JavaScriptCore or Nitro... on Windows we use Chakra or ChakraCore... and on Android and Linux we use Chromium/V8.   Since the Node JavaScript source runs on each without patching (in some cases we add some polyfills), the only things we had to write (once per platform) were the bindings and again really just the primary four (TCP sockets, UDP sockets, timers and the file system).  Others like buffers, cryptography etc., are replaced by javascript only versions (ok for those following this far, actually for cryptography we just didnt like the idea of random generator being the javascript engine variant, so we dip into the OS for just that one random bytes call for improved security, no OpenSSL dependency just native platform)

## Operating Systems

iOS 8+, 9+
OS X, MacOS 10.9, 10.10, 10.11
Windows 10 Universal Platform (October 2015 update or more recent): NKScripting
Swift source 
C# source
Node.js ~0.12.x

## Still In Development

Windows 10 Universal Platform (October 2015 update or more recent): NKCore and NKElectro
Windows 7, Vista, 8, 8.1 for desktop applications
Android
Node.js 4.x/5.x updates (we run a very stable 0.12.x for broadest package compatibility, and are currently testing the 4.x LTS version in a development branch).