# browserify-iced-coffee-coverage

[![Build Status][ci-master]][travis-ci]
[![Coverage Status][coverage-master]][coveralls]
[![Dependency Status][dependency]][david]
[![devDependency Status][dev-dependency]][david]
[![Downloads][downloads]][npm]

A browserify transform to take `.coffee` files and compile them into `.js` with coverage instrumentation using
[iced-coffee-coverage](https://github.com/nextorigin/iced-coffee-coverage). `iced-coffee-coverage` supports
[istanbul](https://github.com/gotwarlost/istanbul) and [jscoverage](http://siliconforks.com/jscoverage/)

[![NPM][npm-stats]][npm]

# Usage

```javascript
var coverage = require('browserify-iced-coffee-coverage');
var b = browserify();
b.add('./foo.coffee');
var options = { noInit: false };
b.transform(coverage, options);
b.bundle();
```

# Options

You can pass anything that you would pass to the `iced-coffee-coverage` constructor, as well as these specific transform
options.

## `options.noInit`

`iced-coffee-coverage` instruments your coffee with lines like `__coverage__["./foo.coffee"].s[1]++;`. For each file, it will
 produce the intialization code to make sure `__coverage__` (In this case the `istanbul` global coverage var) is
 properly setup. You can either choose to either have this initialization code inlined into the transformed file, or
 omit it. There are cases where you might want to omit it, and grab it yourself.

 defaults to `false`.


  [ci-master]: https://img.shields.io/travis/nextorigin/browserify-iced-coffee-coverage/master.svg?style=flat-square
  [travis-ci]: https://travis-ci.org/nextorigin/browserify-iced-coffee-coverage
  [coverage-master]: https://img.shields.io/coveralls/nextorigin/browserify-iced-coffee-coverage/master.svg?style=flat-square
  [coveralls]: https://coveralls.io/r/nextorigin/browserify-iced-coffee-coverage
  [dependency]: https://img.shields.io/david/nextorigin/browserify-iced-coffee-coverage.svg?style=flat-square
  [david]: https://david-dm.org/nextorigin/browserify-iced-coffee-coverage
  [dev-dependency]: https://img.shields.io/david/dev/nextorigin/browserify-iced-coffee-coverage.svg?style=flat-square
  [david-dev]: https://david-dm.org/nextorigin/browserify-iced-coffee-coverage#info=devDependencies
  [downloads]: https://img.shields.io/npm/dm/browserify-iced-coffee-coverage.svg?style=flat-square
  [npm]: https://www.npmjs.org/package/browserify-iced-coffee-coverage
  [npm-stats]: https://nodei.co/npm/browserify-iced-coffee-coverage.png?downloads=true&downloadRank=true&stars=true
