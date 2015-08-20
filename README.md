google-geocoder
===============

Wrapper for Google's Geocoder API.


[![NPM Version][npm-image]][npm-url]
[![NPM Downloads][downloads-image]][downloads-url]
[![Build][travis-image]][travis-url]
[![Coverage Status][coveralls-image]][coveralls-url]



## Installation
    $ npm install google-geocoder


## Example
```javascript
var geocoder = require('google-geocoder');

var geo = geocoder({
  key: 'your API key from google',  // Required
  bounds: {                         // Optional. Prefer results within this viewport (See: https://developers.google.com/maps/documentation/geocoding/intro#Viewports)
    southWest: {
      lat: 34.172684,
      lng: -118.604794
    },
    northEast: {
      lat: 34.236144,
      lng: -118.500938
    }
  },
  region: 'uk',                     // Optional. Results are biased to this region (See: https://developers.google.com/maps/documentation/geocoding/intro#RegionCodes)
  componentFilters: [               // Optional. Restrict results to given components (See: https://developers.google.com/maps/documentation/geocoding/intro#ComponentFiltering)
    'administrative_area:Greater London',
    'country:GB'
  ]
});

geo.find('223 Edenbridge Dr, Toronto', function(err, res){

  // process response object

});

```


## Google Geocoding API Usage
* [GeoCoding Documentation](https://developers.google.com/maps/documentation/geocoding)
* [Obtaining an API Key](https://developers.google.com/maps/documentation/geocoding/#api_key)


## Testing

Create file `test\fixtures\google-api-key.js` with content `module.exports = 'your API key from google';` then run `make test`


## Todo
* Add persistant storage model


## License

(The MIT License)

```
Copyright (c) 20014 Big Mountain Ideas + Innovations <jovan@bigmountainideas.com>

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```


[npm-image]: https://img.shields.io/npm/v/google-geocoder.svg
[npm-url]: https://npmjs.org/package/google-geocoder
[downloads-image]: https://img.shields.io/npm/dm/google-geocoder.svg
[downloads-url]: https://npmjs.org/package/google-geocoder
[travis-image]: https://img.shields.io/travis/bigmountainideas/google-geocoder/master.svg
[travis-url]: https://travis-ci.org/bigmountainideas/google-geocoder
[coveralls-image]: https://coveralls.io/repos/bigmountainideas/google-geocoder/badge.svg?branch=master
[coveralls-url]: https://coveralls.io/r/bigmountainideas/google-geocoder?branch=master
