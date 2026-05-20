Sparkplug Payload
=========

> **Fork:** This package is published on npm as [`@nortech/sparkplug-payload`](https://www.npmjs.com/package/@nortech/sparkplug-payload), maintained by [Nortech AI](https://github.com/Nortech-ai) as a fork of Eclipse Tahu [`sparkplug-payload`](https://www.npmjs.com/package/sparkplug-payload). Upstream project: [eclipse/tahu](https://github.com/eclipse/tahu). Source for this package: [`javascript/core/sparkplug-payload`](https://github.com/Nortech-ai/tahu/tree/master/javascript/core/sparkplug-payload) in the [Nortech AI tahu](https://github.com/Nortech-ai/tahu) repository.

A library that provides tools for encoding and decoding payload objects using
the Sparkplug Google Protocol Buffer Schema described in the Sparkplug 
Specification from Cirrus Link Solutions.

https://s3.amazonaws.com/cirrus-link-com/Sparkplug+Topic+Namespace+and+State+ManagementV2.1+Apendix++Payload+B+format.pdf

## Installation

```bash
npm install @nortech/sparkplug-payload
```

If you use the upstream unscoped package, switch the dependency and module path:

| Upstream | This fork |
|----------|-----------|
| `npm install sparkplug-payload` | `npm install @nortech/sparkplug-payload` |
| `require('sparkplug-payload')` | `require('@nortech/sparkplug-payload')` |

## Usage

This library supports the Sparkplug Google Protocol Buffer Schemas for the
following Sparkplug namespaces:

* spBv1.0
* spAv1.0 (deprecated)


### Encoding a payload

Here is a code example of encoding a payload:

```javascript
var sparkplug = require('@nortech/sparkplug-payload').get("spBv1.0"),
    payload = {
        "timestamp" : new Date().getTime(),
        "metrics" : [
            {
                "name" : "intMetric",
                "value" : 1,
                "type" : "Int32"
            }
        ]
    },
    encoded = sparkplug.encodePayload(payload);
```

### Decoding a payload

Here is a code example of decoding an encoded payload:

```javascript
var decoded = sparkplug.decodePayload(encoded);
```

## Release History

* 1.0.0 Initial release
* 1.0.1 Bug fixes
* 1.0.2 Bug fixes, added typescript
* 1.0.3 Bug fixes

## License

Copyright (c) 2017-2023 Cirrus Link Solutions and others

All rights reserved. This program and the accompanying materials
are made available under the terms of the Eclipse Public License v1.0
which accompanies this distribution, and is available at
http://www.eclipse.org/legal/epl-v10.html

Contributors: Cirrus Link Solutions and others

This fork is maintained by Nortech AI. It is not the official Eclipse Tahu npm package.
