# get-sri

[![Travis CI - Build Status][travis-badge]][travis-url]
[![AppVeyor CI - Build Status][appveyor-badge]][appveyor-url]
[![Coveralls - Code Coverage Status][cov-badge]][cov-url]
[![JavaScript Style Guide][jsstd-badge]][jsstd-url]
[![PRs Welcome][pr-badge]][pr-url]

Generates the [**SRI**][sri-url] [*(Subresource Integrity)*][sri-url] of the given string 
to use as the **SRIs of CDN files** without publishing the content to CDN 
*(e.g. when generating the readme file before release and publish)*.

With `get-sri`, you can just simply generate the `sha256-j7UhB[...]5ni2s=` part of the `integrity` attribute
for `<link>` and `<script>` elements, e.g.: 

```html
<script src="https://cdn.mycustom.com/javascript-file-from-cdn.min.js" 
        integrity="sha256-j7UhB8zxegHMV59uYb38Ho75sqloISge2+fsjN5ni2s=" 
        crossorigin="anonymous"></script>
```

## Installation

```bash
# Using NPM
npm install get-sri --save-dev
```

```bash
# Using Yarn
yarn add get-sri --dev
```

## Usage

```javascript
const getSRI = require('get-sri')

// returns the SRI hash without prefix ('sha256' by default)
getSRI('... file content as string ...') // 'OXPgIukyI[...]6SgMU3pmfURI='

// returns the SRI hash with prefix ('sha256' by default, can be 'sha256', 'sha384', or 'sha512')
getSRI('... file content as string ...', getSRI.SHA256, true) // 'sha256-OXPgIukyI[...]6SgMU3pmfURI='
```

## Contribution

**Any contribution is appreciated**. To get going, check out the 
[**contribution guidelines**](CONTRIBUTING.md) and the 
[**development guide**](DEVELOPMENT.md). 

***Thank you, have fun!***

## License

[MIT](LICENSE.md) @ [Richard Szakacs](https://www.github.com/richardszkcs)


  [travis-badge]:   https://travis-ci.org/ntbx/get-sri.svg?branch=master
  [travis-url]:     https://travis-ci.org/ntbx/get-sri
  [appveyor-badge]: https://ci.appveyor.com/api/projects/status/09qmd4yk9arxyeph?svg=true
  [appveyor-url]:   https://ci.appveyor.com/project/richardszkcs/get-sri

  [cov-badge]:      https://coveralls.io/repos/github/ntbx/get-sri/badge.svg?branch=master
  [cov-url]:        https://coveralls.io/github/ntbx/get-sri?branch=master

  [jsstd-badge]:    https://img.shields.io/badge/code_style-standard-brightgreen.svg
  [jsstd-url]:      https://standardjs.com
  
  [pr-badge]:       https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square
  [sri-url]:        https://hacks.mozilla.org/2015/09/subresource-integrity-in-firefox-43
  [pr-url]:         CONTRIBUTING.md
