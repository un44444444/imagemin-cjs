# imagemin-cjs

> Minify images seamlessly,
> imagemin-cjs commonjs

<br>

---

<br>

## Install

```
$ npm install imagemin-cjs
```

## Usage

```js
const imagemin = require('imagemin-cjs/cjs');
const imageminJpegtran = require('imagemin-jpegtran');
const imageminPngquant = require('imagemin-pngquant');

const files = await imagemin(['images/*.{jpg,png}'], {
	destination: 'build/images',
	plugins: [
		imageminJpegtran(),
		imageminPngquant({
			quality: [0.6, 0.8]
		})
	]
});

console.log(files);
//=> [{data: <Buffer 89 50 4e …>, destinationPath: 'build/images/foo.jpg'}, …]
```

## API

### imagemin(input, options?)

Returns `Promise<object[]>` in the format `{data: Buffer, sourcePath: string, destinationPath: string}`.

#### input

Type: `string[]`

File paths or [glob patterns](https://github.com/sindresorhus/globby#globbing-patterns).

#### options

Type: `object`

##### destination

Type: `string`

Set the destination folder to where your files will be written. If no destination is specified, no files will be written.

##### plugins

Type: `Array`

[Plugins](https://www.npmjs.com/browse/keyword/imageminplugin) to use.

##### glob

Type: `boolean`\
Default: `true`

Enable globbing when matching file paths.

### imagemin.buffer(buffer, options?)

Returns `Promise<Buffer>`.

#### buffer

Type: `Buffer`

Buffer to optimize.

#### options

Type: `object`

##### plugins

Type: `Array`

[Plugins](https://www.npmjs.com/browse/keyword/imageminplugin) to use.

## Related

- [imagemin-cli](https://github.com/imagemin/imagemin-cli) - CLI for this module
- [imagemin-app](https://github.com/imagemin/imagemin-app) - GUI app for this module
- [gulp-imagemin](https://github.com/sindresorhus/gulp-imagemin) - Gulp plugin
- [grunt-contrib-imagemin](https://github.com/gruntjs/grunt-contrib-imagemin) - Grunt plugin
