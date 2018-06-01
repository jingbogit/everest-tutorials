# Babel

### installation

```
yarn add -D babel-core babel-cli babel-eslint babel-plugin-add-module-exports babel-plugin-transform-es2015-modules-umd babel-preset-env
```

### configurations

config file `.babelrc` for browser:

```
{
  "presets": [
    ["es2015", {"modules": false}],
    ["env", {
      "targets": {
        "browsers": ["last 2 versions", "safari >= 7", "ie >= 8", "> 1% in CN", "> 3% in US"]
      }
    }]
  ]
}
```

### polyfills that are not in babel

Babel doesn't provide polyfills for certain methods. You will need to polyfill these to support IE.

* promise
* CustomEvent
* Int8Array.from



