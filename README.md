# LightRPC
Tiny JSON-RPC library - batteries not included.

[![build status](https://img.shields.io/travis/Sekhmet/lightrpc/master.svg?style=flat-square)](https://travis-ci.org/Sekhmet/lightrpc)
[![npm version](https://img.shields.io/npm/v/lightrpc.svg?style=flat-square)](https://www.npmjs.com/package/lightrpc)
[![npm downloads](https://img.shields.io/npm/dm/lightrpc.svg?style=flat-square)](https://www.npmjs.com/package/lightrpc)

**This project is not stable yet!**

## Getting Started

LightRPC is a minimal library for interacting with JSON RPC.
It is designed to be small and work in browser and server.

### Installing

#### Install using npm or yarn
```bash
npm install lightrpc
# or if you are using yarn
yarn add lightrpc
```

#### Obtain development copy

```bash
git clone https://github.com/Sekhmet/lightrpc.git
cd lightrpc
npm install
```

## Usage

#### Usage in browser
```html
<script src="https://unpkg.com/lightrpc/dist/lightrpc.js"></script>
```
Or if you want to use not minified version
```html
<script src="https://unpkg.com/lightrpc/dist/lightrpc.min.js"></script>
```

```js
// using UMD (browser)
const client = window.LightRPC.createClient('https://api.steemit.com');

// using CommonJS
const createClient = require('lightrpc').createClient;
const client = createClient('https://api.steemit.com');

// using ES6 modules
import { createClient } from 'lightrpc';
const client = createClient('https://api.steemit.com');

// sending requests
client.send('get_accounts', [usernames], function(err, result) {
  if (err !== null) console.error(err);
  console.log('response', result);
});
```

#### Options
You can configure client by using optional options parameter to `createClient`.
```js
const options = {
  timeout: 5000,
};

const client = createClient('https://api.steemit.com', options);
```

| Option  | Default value                          | Description                         |
|---------|----------------------------------------|-------------------------------------|
| timeout | 5000                                   | Time after request should timeout.  |
| headers | `{'Content-Type': 'application/json'}` | Headers to be included in requests. |
## Running the tests

You can run lint and tests using npm script

```
npm run test
```


## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/Sekhmet/lightrpc).

## Authors

* **Wiktor Tkaczyński** - [Sekhmet](https://github.com/Sekhmet)

See also the list of [contributors](https://github.com/Sekhmet/lightrpc/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
