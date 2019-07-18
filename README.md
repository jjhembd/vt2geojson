Dump vector tiles to GeoJSON from remote URLs or local system files.

## Installation

```
npm install -g jjhembd/vt2geojson
```

## Usage

Node.js

```javascript
var vt2geojson = require('@mapbox/vt2geojson');

// remote file
vt2geojson({
    uri: 'http://api.example.com/9/150/194.mvt',
    layer: 'layer_name'
}, function (err, result) {
    if (err) throw err;
    console.log(result); // => GeoJSON FeatureCollection
});

// local file
vt2geojson({
    uri: './local/file/buffer.mvt',
    layer: 'layer_name',
    size: 512
}, function (err, result) {
    if (err) throw err;
    console.log(result); // => GeoJSON FeatureCollection
});
```

CLI

```
Usage: vt2geojson [options] URI

Options:
  -l, --layer  include only the specified layer
  -size        pixel size of the rendered tile
  -h, --help   Show help  [boolean]

Examples:
  vt2geojson --layer state_label https://api.mapbox.com/v4/mapbox.mapbox-streets-v6/9/150/194.vector.pbf?access_token=${MAPBOX_ACCESS_TOKEN}
```
