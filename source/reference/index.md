---
title: "NKScripting"
description: "The NKScripting API"
---
## Installation 

Use Carthage (`nodekit-io/nodekit-darwin`) or CocoaPods (`NodeKit/NKScripting`)

Note: NKScripting has no other external dependencies.  

## API

###  NKScriptContextFactory

``` Swift

let options = Dictionary<String, AnyObject>()

NKScriptContextFactory().createScriptContext(options, delegate: self.scriptContextDelegate)

```


### NKScriptContextDelegate

``` Swift

func NKScriptEngineDidLoad(context: NKScriptContext) -> Void 

func NKScriptEngineReady(context: NKScriptContext) -> Void {

```


### NKScriptContext

``` Swift

func loadPlugin(object: AnyObject, namespace: String, options: Dictionary<String, AnyObject>) -> Void

func evaluateJavaScript(javaScriptString: String, completionHandler: ((AnyObject?,NSError?) -> Void)?)

```

### Native Plugins that are exposed to JavaScript

Example to create plugin

`context.loadPlugin(storage(), namespace: "io.nodekit.scripting.storage", options: ["js": "lib-scripting.nkar/lib-scripting/native_module.js"])`

Plugins should implement an @objc protocol that injerits from NKScriptExport;  each method in this protocol is exposed automatically to JavaScript

See SamplePlugin.swift for an example
