# Symmetric Crypto (NodeJS)

[`SymmetricCrypto.NodeJS`](https://github.com/hugoalh-studio/symmetric-crypto-nodejs)
[![GitHub Contributors](https://img.shields.io/github/contributors/hugoalh-studio/symmetric-crypto-nodejs?label=Contributors&logo=github&logoColor=ffffff&style=flat-square)](https://github.com/hugoalh-studio/symmetric-crypto-nodejs/graphs/contributors)
[![GitHub Issues](https://img.shields.io/github/issues-raw/hugoalh-studio/symmetric-crypto-nodejs?label=Issues&logo=github&logoColor=ffffff&style=flat-square)](https://github.com/hugoalh-studio/symmetric-crypto-nodejs/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr-raw/hugoalh-studio/symmetric-crypto-nodejs?label=Pull%20Requests&logo=github&logoColor=ffffff&style=flat-square)](https://github.com/hugoalh-studio/symmetric-crypto-nodejs/pulls)
[![GitHub Discussions](https://img.shields.io/github/discussions/hugoalh-studio/symmetric-crypto-nodejs?label=Discussions&logo=github&logoColor=ffffff&style=flat-square)](https://github.com/hugoalh-studio/symmetric-crypto-nodejs/discussions)
[![GitHub Stars](https://img.shields.io/github/stars/hugoalh-studio/symmetric-crypto-nodejs?label=Stars&logo=github&logoColor=ffffff&style=flat-square)](https://github.com/hugoalh-studio/symmetric-crypto-nodejs/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/hugoalh-studio/symmetric-crypto-nodejs?label=Forks&logo=github&logoColor=ffffff&style=flat-square)](https://github.com/hugoalh-studio/symmetric-crypto-nodejs/network/members)
![GitHub Languages](https://img.shields.io/github/languages/count/hugoalh-studio/symmetric-crypto-nodejs?label=Languages&logo=github&logoColor=ffffff&style=flat-square)
[![CodeFactor Grade](https://img.shields.io/codefactor/grade/github/hugoalh-studio/symmetric-crypto-nodejs?label=Grade&logo=codefactor&logoColor=ffffff&style=flat-square)](https://www.codefactor.io/repository/github/hugoalh-studio/symmetric-crypto-nodejs)
[![License](https://img.shields.io/static/v1?label=License&message=MIT&style=flat-square)](./LICENSE.md)

| **Release** | **Latest** (![GitHub Latest Release Date](https://img.shields.io/github/release-date/hugoalh-studio/symmetric-crypto-nodejs?label=%20&style=flat-square)) | **Pre** (![GitHub Latest Pre-Release Date](https://img.shields.io/github/release-date-pre/hugoalh-studio/symmetric-crypto-nodejs?label=%20&style=flat-square)) |
|:-:|:-:|:-:|
| [**GitHub**](https://github.com/hugoalh-studio/symmetric-crypto-nodejs/releases) ![GitHub Total Downloads](https://img.shields.io/github/downloads/hugoalh-studio/symmetric-crypto-nodejs/total?label=%20&style=flat-square) | ![GitHub Latest Release Version](https://img.shields.io/github/release/hugoalh-studio/symmetric-crypto-nodejs?sort=semver&label=%20&style=flat-square) | ![GitHub Latest Pre-Release Version](https://img.shields.io/github/release/hugoalh-studio/symmetric-crypto-nodejs?include_prereleases&sort=semver&label=%20&style=flat-square) |
| [**NPM**](https://www.npmjs.com/package/@hugoalh/symmetric-crypto) ![NPM Total Downloads](https://img.shields.io/npm/dt/@hugoalh/symmetric-crypto?label=%20&style=flat-square) | ![NPM Latest Release Version](https://img.shields.io/npm/v/@hugoalh/symmetric-crypto/latest?label=%20&style=flat-square) | ![NPM Latest Pre-Release Version](https://img.shields.io/npm/v/@hugoalh/symmetric-crypto/pre?label=%20&style=flat-square) |

## 📝 Description

A NodeJS module to provide an easier symmetric crypto.

*This project is inspired from `symencdec` ([GitHub](https://github.com/nire0510/symencdec))([NPM](https://www.npmjs.com/package/symencdec)).*

Symmetric crypto is a password based encryption and decryption, but this module has some addition improvements.

## 📚 Documentation

*For the official documentation, please visit [GitHub Repository Wiki](https://github.com/hugoalh-studio/symmetric-crypto-nodejs/wiki).*

### Getting Started (Excerpt)

#### Install

- NodeJS >= v12.13.0
- NPM >= v6.12.0

```sh
npm install @hugoalh/symmetric-crypto
```

#### Use In CommonJS

```js
const symmetricCrypto = require("@hugoalh/symmetric-crypto");
```

#### Use In ModuleJS

```js
/* Either */
import * as symmetricCrypto from "@hugoalh/symmetric-crypto";// All
import symmetricCrypto from "@hugoalh/symmetric-crypto";// All (>= v1.3.1)
import { ... } from "@hugoalh/symmetric-crypto";// Part / Tree-shake
```

### API (Excerpt)

#### Class

- `SymmetricCryptor`
  - `@constructor(passphrase)`
  - `decrypt(data, times?)`
  - `decryptMultipleLine(data, times?)`
  - `encrypt(data, times?)`
  - `encryptMultipleLine(data, times?)`

#### Function

- `decrypt(data, passphrase, times?)`
- `decryptMultipleLine(data, passphrase, times?)`
- `encrypt(data, passphrase, times?)`
- `encryptMultipleLine(data, passphrase, times?)`

### Example (Excerpt)

```js
let data = "Hello, world!\nFoo.\nBar.";
let passphrase = "githubnode";
let firstEncrypted = symmetricCrypto.encrypt(data, passphrase);
let secondEncrypted = symmetricCrypto.encryptMultipleLine(data, passphrase);
console.log(firstEncrypted);
// "TIdMOTTeor6q79ilfKkcInvWqQ/U4UUK5oXRSXxWhTbNpL88i/QDly9NFCt1d6JwkDWJ0nkLGKwsWbcA6tM2yg=="

console.log(secondEncrypted);
/*
`LO1uspz3yPXlbDdi20Xk5kYPc06kZO3h0SH6mN+gCI/+xTRpeanWPNat17ufGpxE
NdLVDbUWDAeBK1MdXoO4rIbpBbwiCyaPU0ut8HOCCLXnidGM9EEbevuL8EGjQVSS
nh3fuCzHOXWhtBLHuIZyiz5n9/Om0uPZdHdEikei8ydjnpaVLaCT2p78Uamxc3m1`
*/

let firstDecrypted = symmetricCrypto.decrypt(firstEncrypted, passphrase);
let secondDecrypted = symmetricCrypto.decryptMultipleLine(secondEncrypted, passphrase);
console.log(firstDecrypted);
// "Hello, world!\nFoo.\nBar."

console.log(secondDecrypted);
// "Hello, world!\nFoo.\nBar."
```
