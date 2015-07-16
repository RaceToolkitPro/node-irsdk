﻿# Node.js iRacing SDK

The first, experimental, version will support session data and live telemetry only.

## Requirements and Install

You need Windows version of [Node.js](https://nodejs.org/download/). And because 
node-gyp is used to compile C++ module, you have to 
install its dependencies. Having Python 2.7 in PATH and some version of Visual Studio 
should be enough but check 
[installation instructions of node-gyp](https://github.com/TooTallNate/node-gyp) 
if node-gyp fails.

node-irsdk can be installed from GitHub using command:

`npm install --save apihlaja/node-irsdk`


## API


### Event: 'Connected'

Emitted when iRacing SDK is available.


### Event: 'Disconnected'

Emitted when iRacing SDK access is lost ie. when sim is shut down. 
The `'Connected'` event is emitted again if sim is restarted.


### Event: 'TelemetryDescription'

* `function (data) { }`

Emitted when first telemetry sample is received after connecting. 
See example of `data` object here: [telemetry-desc.json](sample-data/telemetry-desc.json).


### Event: 'Telemetry'

* `function (data) { }`

Emitted always when new telemetry sample is received. 
See example of `data` object here: [telemetry.json](sample-data/telemetry.json).


### Event: 'SessionInfo'

* `function (data) { }`

Emitted always when new SessionInfo is changed. `data` has two properties: raw and doc.
`raw` is orginal yaml string from iRacing, see example here: [sessioninfo.yaml](sample-data/sessioninfo.yaml).
`doc` is Object with same data, see example here: [sessioninfo.json](sample-data/sessioninfo.json).


