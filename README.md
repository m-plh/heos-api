# heos-api

[![npm](https://img.shields.io/npm/v/heos-api.svg?style=flat-square)](https://www.npmjs.com/package/heos-api)
[![npm](https://img.shields.io/npm/dm/localeval.svg?style=flat-square)](https://www.npmjs.com/package/heos-api)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square)](https://github.com/juliuscc/heos-api/blob/master/LICENSE)
[![Codecov](https://img.shields.io/codecov/c/github/codecov/example-python.svg?style=flat-square)](https://codecov.io/gh/juliuscc/heos-api)
[![Travis](https://img.shields.io/travis/rust-lang/rust.svg?style=flat-square)](https://travis-ci.org/juliuscc/heos-api)

A low level Node.js api-wrapper for communicating with heos devices. It enables developers to find, connect to, and communicate with Heos Devices.

-   🔎 **Discover devices:** Dead simple discovery of heos devices.
-   🎯 **Send any command:** Send commands with a simple api.
-   🛰 **Event handling:** React to anything that happens to your heos control system, by binding any event to one or more callbacks.

## Upgrading from 2.X.X

The module changed a lot from version 2 to version 3. The underlying communication handlers were rebuilt and the high level commands and promise based wrappers were removed, to better focus the package on providing a great communication library. The high level features will be implemented in [heos-client](https://www.npmjs.com/package/heos-client), and can still be accessed by downloading version 2 of this package.

```
npm install --save heos-api@^2.0.0
```

## Getting started

Install heos-api using `npm`:

```
npm install --save heos-api
```

Let's get started with connecting to a heos control system:

```js
const heos = require('heos-api')

heos.discoverOne()
	.then(address => heos.connect(address))
	.then(() => console.log('Connection established! 🌈'))
```

To send a command just use one of the predefined heos-api functions. The response will resolve the promise:

```js
const heos = require('heos-api')

heos.discoverOne()
	.then(address => heos.connect(address))
	.then(connection => connection.write('system', 'heart_beat'))
```

Commands that require parameters works as well:

```js
const heos = require('heos-api')

heos.discoverOne()
	.then(address => heos.connect(address))
	.then(connection => connection.write(
		'system',
		'prettify_json_response',
		{ enable: on }
	))
)
```

## Documentation

Learn more about using heos-api at:

-   ~~API reference~~ 🚧 Under construction 🚧
-   ~~Guides~~ 🚧 Under construction 🚧
-   [The GitHub page](https://github.com/juliuscc/heos-api)
-   [HEOS CLI Protocol Specification](http://rn.dmglobal.com/euheos/HEOS_CLI_ProtocolSpecification.pdf)

## Contributing

Please send issues and pull requests with your problems or ideas.
