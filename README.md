![nails-framework](https://f.cloud.github.com/assets/1144357/2225403/4529567e-9a8d-11e3-80a4-23ba637b5f26.png)

# nails-image
*Image manipulation utils service for [nails-framework](http://ghub.io/nails-framework)*

Provides [gm](https://ghub.io/gm) with some convenience methods.

## Install
```bash
$ npm i -s nails-image
```

## Example
```javascript
// Load the plugin before calling app.start()
app.plugin('nails-image');

app.service('image')
    .fetch({
      url: 'http://www.fillmurray.com/g/750/500',    // or file: '/photos/bill/2015/04/01/bill.jpg'
      filename: 'bill.jpg'
    })
    .overlay({
      width: 650,
      height: 650,
      background: transparent,
      file: 'my-transparent-watermark.png'           // url isn't yet supported here
    })
    .quality(85)
    .compress('JPEG')
    .write(outputPath, cb);
```

See the [gm documentation](https://ghub.io/gm) for more information.

## License

The MIT License (MIT)

Copyright (c) 2015 James Wyse <james@jameswyse.net>

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
