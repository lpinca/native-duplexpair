duplexpair
==============

[![NPM Version](https://img.shields.io/npm/v/native-duplexpair.svg?style=flat)](https://npmjs.org/package/native-duplexpair)
[![NPM Downloads](https://img.shields.io/npm/dm/native-duplexpair.svg?style=flat)](https://npmjs.org/package/native-duplexpair)
[![Build Status](https://travis-ci.org/tediousjs/native-duplexpair.svg?style=flat&branch=master)](https://travis-ci.org/tediousjs/native-duplexpair?branch=master)
[![Coverage Status](https://coveralls.io/repos/tediousjs/native-duplexpair/badge.svg?branch=master)](https://coveralls.io/r/tediousjs/native-duplexpair?branch=master)
[![Dependency Status](https://david-dm.org/tediousjs/native-duplexpair.svg?style=flat)](https://david-dm.org/tediousjs/native-duplexpair)

Make a full duplex stream with 2 Duplex endpoints.

**Note:**

This is a fork of `duplexpair`, changed to use the "native" `Duplex` stream that is part
of Node.JS instead of the version from the `readable-stream` package.

Install:
`npm install native-duplexpair`

```js
const DuplexPair = require('native-duplexpair');

const { socket1, socket2 } = new DuplexPair();

socket1.write('Hi');
console.log(socket2.read());  // => <Buffer 48 69>

// Or, using options that are passed to the Duplex constructor:

const { socket1, socket2 } = new DuplexPair({ encoding: 'utf8' });

socket1.write('Hi');
console.log(socket2.read());  // => 'Hi'
```

License
=======

MIT
