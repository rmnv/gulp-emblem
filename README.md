# gulp-emblem [![NPM version][npm-image]][npm-url] [![Build status][travis-image]][travis-url]
> [Emblem.js][emblem-url] plugin for gulp
> ...a concise, beautiful, and fully compatible templating alternative for Handlebars.js.

## Usage

First, install _gulp-emblem_ and [gulp-define-module] as development dependencies:

```shell
npm install --save-dev gulp-emblem gulp-define-module
```

Then, add it to your `gulpfile.js`:

```javascript
var emblem = require('gulp-emblem');
var defineModule = require('gulp-define-module');

gulp.task('templates', function(){
  gulp.src(['client/templates/*.em'])
    .pipe(emblem())
    .pipe(defineModule('node'))
    .pipe(gulp.dest('build/templates/'));
});
```

gulp-emblem outputs a raw handlebars function, so it is likely that you will want to use [gulp-define-module] to make the handlebars template available via a specific namespace or for use with a module system. For additional usage examples, we recommend that you visit [gulp-handlebars] and [gulp-define-module].


## Compiling to various module systems

[gulp-define-module] can be used to prepare the output for use with common module systems such as AMD, Node, and CommonJS. Please see the documentation for more details on how to use that in a gulp chain.

gulp-emblem makes the following available for use in the [define-module wrapper](https://github.com/wbyoung/gulp-define-module#optionswrapper):

 - `handlebars`: The handlebars template fully wrapped (`Handlebars.template(<%= contents %>)`).


## API

### emblem(options)

#### options.compilerOptions
Type: `Object`

Compiler options to pass to `Emblem.precompile()`.

## Attributions
This project is a fork of [`gulp-handlebars`](https://github.com/lazd/gulp-handlebars) by [lazd](https://github.com/lazd).
[Emblem.js][emblem-url] is a concise, beautiful, and fully compatible templating alternative for Handlebars.js.


[travis-url]: http://travis-ci.org/Aulito/gulp-emblem
[travis-image]: https://secure.travis-ci.org/Aulito/gulp-emblem.png?branch=master
[npm-url]: https://npmjs.org/package/gulp-emblem
[npm-image]: https://badge.fury.io/js/gulp-emblem.png

[gulp-define-module]: https://github.com/wbyoung/gulp-define-module
[gulp-handlebars]: https://github.com/lazd/gulp-handlebars
[emblem-url]: http://emblemjs.com/
