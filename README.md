Flora-Api
======

[![Software License](https://img.shields.io/badge/license-GPL--3.0-brightgreen.svg?style=flat-square)](LICENSE)
[![npm](https://img.shields.io/npm/v/flora-api.svg?style=flat-square)](https://libraries.io/npm/flora-api)

## Usage example

```js
const { readFileSync } = require('fs');
const { Connection, constants, ApiClient } = require('flora-api');

(async () => {
  const conn = new Connection('localhost:55422', {
    cert: readFileSync('private_daemon.crt'),
    key: readFileSync('private_daemon.key'),
  });
  conn.onMessage((message) => {
    console.log(message);
  });
  conn.addService(constants.SERVICE().walletUi);
  const fullNode = new ApiClient.FullNode({ connection: conn, origin: 'my-cool-service' });
  await fullNode.init();
  const blockchainState = await fullNode.getBlockchainState();
})();
```

## Donate

Forked From Felixbruckers Hard Work I CopyPasta Modded This All Hard Work Still Done By Felix His Address Are Below:
- ETH: 0xfEc6F48633A7c557b4ac5c37B4519C55CD701BEF
- BTC: 14rbdLr2YXDkguVaqRKnPftTPX52tnv2x2
- PP: https://www.paypal.me/felixbrucker

## Changelog

A Changelog can be found [here](https://github.com/MinerGreggy/flora-api/blob/master/CHANGELOG.md)

## License

GNU GPLv3 (see [LICENSE](https://github.com/MinerGreggy/flora-api/blob/master/LICENSE))
