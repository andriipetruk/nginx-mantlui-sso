# brunch-signature

[Brunch][] plugin that generates a unique signature as part of the `brunch
build` process. The signature changes whenever any file in the project is
modified.

I am using brunch-signature to alert users when a new version of the app has
been deployed. I Ajax poll `/signature` and check for a difference form the
value when the app first started. When it's different, I show a banner telling
the user to refresh.

## Usage

Install the plugin via npm with `npm install --save brunch-signature`.

Or, do manual install:

* Add `"brunch-signature": "x.y.z"` to `package.json` of your brunch app.
  Pick a plugin version that corresponds to your minor (y) brunch version.
* If you want to use git version of plugin, add
`"brunch-signature": "git+ssh://git@github.com:mutewinter/brunch-signature.git"`.

_Optional_ Specify [plugin settings](#settings) in config.coffee. For example:

```coffeescript
exports.config =
  # ...
  plugins:
    signature:
      file: 'signature'
      ignore: /[\\/][.]/
```

## Settings

### signature.ignore

A regular expression specifying paths to omit from the signature.

Default value : `/[/][.]/` (hidden files and files in hidden directories are ignored)

### signature.file

Output filename. For example:

```coffeescript
file: "app.signature"
```

Default value : `"signature"`

## License

The MIT License (MIT)

Copyright (c) 2013 Jeremy Mack @mutewinter

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

[Brunch]: http://brunch.io
