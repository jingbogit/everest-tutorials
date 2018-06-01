### Webpack

webpack bundled all the small pieces of js file \(including other files\) into one large js file.



### BundleAnalyzer

[Optimising your application bundle size with webpack](https://hackernoon.com/optimising-your-application-bundle-size-with-webpack-e85b00bab579)

To use it in webpack:

```
plugins: [
  new BundleAnalyzerPlugin({
    analyzerMode: 'static'
  })
]
```

### external

You may want to exclude some large dependency out of your bundled js file.

### Uglify

webpack 4 will do this by default in production mode.

## configuration

A sample config file

```
const path = require('path')
const BundleAnalyzerPlugin = require('webpack-bundle-analyzer').BundleAnalyzerPlugin

module.exports = {
  mode: 'production',
  entry: {
    'engine': './src/engine.js'
  },
  output: {
    path: path.resolve(__dirname, 'release'),
    filename: 'altizure-gl-engine.min.js',
    library: 'engine',
    libraryTarget: 'umd'
  },
  module: {
  },
  plugins: [
    new BundleAnalyzerPlugin({
      analyzerMode: 'static'
    })
  ]
}

```



