turf-isolines
=============
[![Build Status](https://travis-ci.org/Turfjs/turf-isolines.svg?branch=master)](https://travis-ci.org/Turfjs/turf-isolines)

Takes a FeatureCollection of points with z values and an array of value breaks and generates isolines. These are commonly used to create elevation maps, but can be used for general data interpolation as well.

###Install

```sh
npm install turf-isolines
```

###Parameters

|name|description|
|---|---|
|points|points use as seed values|
|z|z value to contour|
|resolution|resolution of the underlying grid|
|breaks|where to draw contours|

###Usage

```js
isolines(points, z, resolution, breaks)
```

###Example

```js
var isolines = require('turf-isolines')
var fs = require('fs')

var z = 'elevation'
var resolution = 15
var breaks = [.1, 22, 45, 55, 65, 85,  95, 105, 120, 180]
var points = JSON.parse(fs.readFileSync('/path/to/points.geojson'))

var isolined = isolines(points, z, resolution, breaks)

console.log(isolined)
```