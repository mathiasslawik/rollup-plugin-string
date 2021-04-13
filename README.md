# rollup-plugin-string [![Build Status](https://travis-ci.org/TrySound/rollup-plugin-string.svg)](https://travis-ci.org/TrySound/rollup-plugin-string)

Converts text files to modules:

```js
import tpl from "./tpl.html";
console.log(`Template for render: ${tpl}`);
```

## Installation

```sh
npm i rollup-plugin-string -D
```

## Usage

```js
import { rollup } from "rollup";
import { string } from "rollup-plugin-string";

rollup({
  entry: "main.js",
  plugins: [
    string({
      // Required. Only process files matching this minimatch pattern.
      include: "**/*.html",

      // Optional (default: undefined). Exclude these files from being processed.
      exclude: ["**/index.html"]
    })
  ]
});
```

The `include` and `exclude` parameters are passed to the [createFilter](https://github.com/rollup/rollup-pluginutils#createfilter) method of rollup-pluginutils.

Note: relative paths are resolved against `process.cwd()`, i.e., the current working directory. Keep this in mind when working, e.g., within monorepos.

# License

MIT © [Bogdan Chadkin](mailto:trysound@yandex.ru)
