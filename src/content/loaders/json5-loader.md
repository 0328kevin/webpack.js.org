---
title: json5-loader
source: https://raw.githubusercontent.com/webpack-contrib/json5-loader/master/README.md
edit: https://github.com/webpack-contrib/json5-loader/edit/master/README.md
repo: https://github.com/webpack-contrib/json5-loader
---
A webpack loader for parsing <a href="http://json5.org/"><code>json5</code></a> files into JavaScript objects.

## Install

```sh
$ npm install --save-dev json5-loader
```

## Usage

You can use the loader either
 * by configuring the `json5-loader` in the `module.loaders` object of the webpack configuration, or
 * by directly using the `json5-loader!` prefix to the require statement.

Suppose we have the following `json5` file
```js
// appData.json5
{
  env: 'production',
  passwordStregth: 'strong'
}
```

###

```js
// webpack.config.js
module.exports = {
  entry: './index.js',
  output: { /* ... */ },
  module: {
    loaders: [
      {
        // make all files ending in .json5 use the `json5-loader`
        test: /\.json5$/,
        loader: 'json5-loader'
      }
    ]
  }
}
```

```js
// index.js
var appConfig = require('./appData.json5')
// or, in ES6
// import appConfig from './appData.json5'

console.log(appConfig.env) // 'production'
```
#### Usage with require statement loader prefix
```js
var appConfig = require("json5-loader!./appData.json5")
// returns the content as json parsed object

console.log(appConfig.env) // 'production'
```

Don't forget to polyfill require if you want to use it in Node.js. See the webpack documentation.

## Maintainers

<table>
  <tbody>
    <tr>
      <td align="center">
        <img width="150" height="150"
        src="https://avatars.githubusercontent.com/sokra?v=3">
        <br />
        <a href="https://github.com/sokra">Tobias Koppers</a>
      </td>
      <td align="center">
        <img width="150" height="150"
        src="https://avatars.githubusercontent.com/gdi2290?v=3">
        <br />
        <a href="https://github.com/gdi2290">PatrickJS</a>
      </td>
      <td align="center">
        <img width="150" height="150" src="https://avatars.githubusercontent.com/Cellule?v=3">
        <br />
        <a href="https://github.com/Cellule">Michael Ferris</a>
      </td>
      <td align="center">
        <img width="150" height="150"
        src="https://avatars.githubusercontent.com/kmck?v=3">
        <br />
        <a href="https://github.com/kmck">Keith McKnight</a>
      </td>
    </tr>
    <tr>
      <td align="center">
        <img width="150" height="150"
        src="https://avatars.githubusercontent.com/radubrehar?v=3">
        <br />
        <a href="https://github.com/radubrehar">Radu Brehar</a>
      </td>
      <td align="center">
        <img width="150" height="150"
        src="https://avatars.githubusercontent.com/kentcdodds?v=3">
        <br />
        <a href="https://github.com/kentcdodds">Kent C. Dodds</a>
      </td>
      <td align="center">
        <img width="150" height="150"
        src="https://avatars.githubusercontent.com/stevelacy?v=3">
        <br />
        <a href="https://github.com/stevelacy">Steve Lacy</a>
      </td>
    </tr>
  </tbody>
</table>

## LICENSE

MIT

[npm]: https://img.shields.io/npm/v/json5-loader.svg
[npm-url]: https://npmjs.com/package/json5-loader

[deps]: https://david-dm.org/webpack-contrib/json5-loader.svg
[deps-url]: https://david-dm.org/webpack-contrib/json5-loader

[chat]: https://img.shields.io/badge/gitter-webpack%2Fwebpack-brightgreen.svg
[chat-url]: https://gitter.im/webpack/webpack

[test]: http://img.shields.io/travis/webpack-contrib/json5-loader.svg
[test-url]: https://travis-ci.org/webpack-contrib/json5-loader

[cover]: https://codecov.io/gh/webpack-contrib/json5-loader/branch/master/graph/badge.svg
[cover-url]: https://codecov.io/gh/webpack-contrib/json5-loader
