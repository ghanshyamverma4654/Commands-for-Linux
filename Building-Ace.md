You do not generally have to build Ace.  The [ace-builds](https://github.com/ajaxorg/ace-builds/) repository usually contains the latest build and you can just copy one of the `src*` subdirectories somewhere into your project.

To build Ace you only need [Node.js](https://nodejs.org/)

just run `npm install` in the ace folder to install the dependencies

and then `node Makefile.dryice.js`

build script accepts the following options:
```js
-m                 minify build files with uglify-js          
-nc                namespace require and define calls with "ace"
--target ./path    specify relative path for output folder (default value is "./build")
```

to build bookmarklet version run `node Makefile.dryice.js bm`

and to generate all the files in ace-builds repository run `node Makefile.dryice.js full --target ../ace-builds`
