# @tufan-io/pkg-ok 
[![action-ci](https://github.com/tufan-io/pkg-ok/actions/workflows/.action_ci.yml/badge.svg)](https://github.com/tufan-io/pkg-ok/actions/workflows/.action_ci.yml)

> Forked from [typicode/pkg-ok](https://github.com/typicode/pkg-ok) to add maintainance updates

> `pkg-ok` checks paths and scripts defined in `package.json` before you publish 👌

* Ensures paths defined in `main`, `bin`, `module`, `types`, `typings`, `es2015` and `browser` exist
* Ensures `bin` scripts use cross-platform line endings

## Usage

```sh
npm install @tufan-io/pkg-ok --save-dev
```

```js
// package.json
{
  "main": "oops_this_file_doesnt_exist.js",
  "scripts": {
    "prepublishOnly": "... && pkg-ok"
  }
}
```

```sh
npm publish
# Error!
# Since main file doesn't exist, publish is blocked 
```

## Options

`pkg-ok` can be configured to check additional `package.json` fields or bin files

```
pkgOk --field someField --bin script.sh
```

## API

```js
const pkgDirectory = __dirname

pkgOk(pkgDirectory, {
  fields: ['someAdditonalField'],
  bin: ['someAdditionalScript.sh']
})
```

## License

MIT

[Patreon](https://www.patreon.com/typicode) - [Supporters](https://thanks.typicode.com) ✨
