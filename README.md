# nodemailer-build-attachment

[![Build Status](https://travis-ci.org/killmenot/nodemailer-build-attachment.svg?branch=master)](https://travis-ci.org/killmenot/nodemailer-build-attachment)
[![Coverage Status](https://coveralls.io/repos/github/killmenot/nodemailer-build-attachment/badge.svg?branch=master)](https://coveralls.io/github/killmenot/nodemailer-build-attachment?branch=master)
[![Dependency Status](https://gemnasium.com/badges/github.com/killmenot/nodemailer-build-attachment.svg)](https://gemnasium.com/github.com/killmenot/nodemailer-build-attachment)
[![npm version](https://badge.fury.io/js/nodemailer-build-attachment.svg)](https://badge.fury.io/js/nodemailer-build-attachment)

Build and stream attachment's content.

Based on [Andris Reinman](https://github.com/andris9)'s work in [buildmail](https://github.com/nodemailer/buildmail).

## Requirements

 - Node.js 4+


## Install

```
npm install nodemailer-build-attachment
```


## Example

```javascript
'use strict';

var BuildAttachment = require('nodemailer-build-attachment');
var fs = require('fs');
var stream = fs.createReadStream('path/to/file.txt');
var options = {
    contentTransferEncoding: 'base64'
};

new BuildAttachment(options).setContent(stream).build(function (err, attachment) {
    console.log(attachment.content.toString()); // base64 encoded string
});

```


## Licence

The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
