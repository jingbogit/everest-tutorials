# Formats

## 3D

* obj
  * [demo](https://altizure.github.io/sdk.examples/2-5-add-promoted-obj/index.html)
  * Gemetry file: [obj format](http://paulbourke.net/dataformats/obj/)

  * Material file: [mtl format](http://paulbourke.net/dataformats/mtl/) 
  * The format is highly abused, many people are using their own variation. The  goal is to support the common and popular schemes.

![](/assets/intermediate-3d-formats-3d-obj.png)

* ab
  * altizure unique format, compressed with obj, mtl, and texture file
  * requires key to be correctly decoded
  * normally 100KB of size for best viewering experience

## 2D

* geojson

  * [demo](https://altizure.github.io/experimental-demo/import-geojson.html)
  * vectorized 2D representation, using longitude and latitude.

  ![](/assets/format-2d-geojson-demo.png)

  * semantic segmentaion mask to geojson

* shapefile



