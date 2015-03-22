[![view on npm](http://img.shields.io/npm/v/grunt-jsdoc-to-markdown.svg)](https://www.npmjs.org/package/grunt-jsdoc-to-markdown)
[![npm module downloads per month](http://img.shields.io/npm/dm/grunt-jsdoc-to-markdown.svg)](https://www.npmjs.org/package/grunt-jsdoc-to-markdown)
[![Build Status](https://travis-ci.org/75lb/grunt-jsdoc-to-markdown.svg?branch=master)](https://travis-ci.org/75lb/grunt-jsdoc-to-markdown)
[![Dependency Status](https://david-dm.org/75lb/grunt-jsdoc-to-markdown.svg)](https://david-dm.org/75lb/grunt-jsdoc-to-markdown)

# New release preview!
I am close to finishing the next version, so feedback is welcome at this point!

Install the preview release:

$ npm install -g grunt-jsdoc-to-markdown@next

Any issues or feedback, let me know! 

Anyway, back to the regular documentation:

# grunt-jsdoc-to-markdown
A grunt plugin for [jsdoc-to-markdown](https://github.com/75lb/jsdoc-to-markdown).

## Install
```sh
$ npm install grunt-jsdoc-to-markdown --save-dev
```

## Usage
Example `Gruntfile.js`:

```js
"use strict";
module.exports = function(grunt) {

    grunt.initConfig({
        jsdoc2md: {
            oneOutputFile: {
                src: "src/*.js",
                dest: "api/documentation.md"
            },
            separateOutputFilePerInput: {
                files: [
                    { src: "src/jacket.js", dest: "api/jacket.md" },
                    { src: "src/shirt.js", dest: "api/shirt.md" }
                ]
            },
            withOptions: {
                options: {
                    index: true
                },
                src: "src/wardrobe.js",
                dest: "api/with-index.md"
            }
        }
    });

    grunt.loadNpmTasks("grunt-jsdoc-to-markdown");
    grunt.registerTask("default", "jsdoc2md");
};
```
