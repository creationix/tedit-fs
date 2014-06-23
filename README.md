tedit-fs
========

A wrapper around tedit's private FS api that provides generator friendly access to the VFS

## Usage

This is meant for the "Eval in main" runtime of the web tedit.  The requires
are relative to your requireing file.  I suggest using submodules for `tedit-fs`
and `gen-run`.  This will run out of the box on stable Firefox since that has
generators today.

```js
var fs = require('./modules/tedit-fs/fs')(__dirname);
var run = require('./modules/gen-run/run');

run(function* () {
  var text = yield* fs.readFile("./somefile.txt");
);
```
