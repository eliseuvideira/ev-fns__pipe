# @ev-fns/pipe

Async stream pipeline

- pipe `(source, ...[...transforms, destination]) => Promise<void>`

## Install

```sh
yarn add @ev-fns/pipe
```

## Usage

```js
const fs = require('fs');
const zlib = require('zlib');
const { pipe } = require("@ev-fns/pipe");

pipe(
  fs.createReadStream("archive.tar"),
  zlib.createGzip(),
  fs.createWriteStream("archive.tar.gz")
).then(() => {
  console.log("finished");
});
```
