![http://nodekit.io](./public/images.banner.png)

## This Repository

{NK} NodeKit is the universal, open-source, embedded engine that provides a full Node.js instance inside desktop and mobile applications for OS X, iOS, Android, and Windows.

For application developers, the backend can be written in pure Node javascript code, the front-end in the architecture of your choice including but not limited to Atom Electron API, Facebook React, Express, etc.)

{NK} NodeKit enables applications developed for Node to developed once and then run without alteration for any of the above platforms as well as in the browser.

This is a refined preview of the technology and is not intended for production use, but is supporting some production app store applications. Use at your own caution. Contributions welcome (details to follow)

## To Re-Build the Documentation

This repository uses [hexo](http://hexo.io) to generate the documentation

Install dependencies:

``` bash
$ git clone https://github.com/nodekit-io/nodekit-docs.git
$ cd nodekit-docs
$ brew install homebrew/science/vips --with-webp --with-graphicsmagick
$ npm install
$ npm install -g hexo-cli
```

Generate:

``` bash
$ npm run clean
$ npm run build
```

Run server:

``` bash
$ hexo server
```

## License

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
Documentation under CC BY-SA 4.0 Copyright (c) 2016 OffGrid Networks
Documentation theme Copyright (c) 2013 Tommy Chen, Hexo Contributors (CC BY 4.0)