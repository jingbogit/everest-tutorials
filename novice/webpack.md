### Webpack

webpack bundled all the small pieces of js file \(including other files\) into one large js file.

[Introduction to Webpack with practical examples](https://www.google.com.hk/search?ei=ue4UW_GBM8r_8gXHhqPoCw&q=webpack+example&oq=webpack+example&gs_l=psy-ab.3..0i7i30k1l10.370145.371580.0.372045.7.7.0.0.0.0.88.463.7.7.0..3..0...1.1.64.psy-ab..0.7.461...0i7i10i30k1.0.yfJGrQaP-6Y)

---

### BundleAnalyzer

[Optimising your application bundle size with webpack](https://hackernoon.com/optimising-your-application-bundle-size-with-webpack-e85b00bab579)

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

---

## conventional configuration

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



