# npmdoc-es6-promise

#### basic api documentation for  [es6-promise (v4.1.0)](https://github.com/stefanpenner/es6-promise#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-es6-promise.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-es6-promise) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-es6-promise.svg)](https://travis-ci.org/npmdoc/node-npmdoc-es6-promise)

#### A lightweight library that provides tools for organizing asynchronous code

[![NPM](https://nodei.co/npm/es6-promise.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/es6-promise)

- [https://npmdoc.github.io/node-npmdoc-es6-promise/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-es6-promise/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-es6-promise/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-es6-promise/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-es6-promise/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-es6-promise/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Yehuda Katz, Tom Dale, Stefan Penner and contributors",
        "url": "Conversion to ES6 API by Jake Archibald"
    },
    "browser": {
        "vertx": false
    },
    "bugs": {
        "url": "https://github.com/stefanpenner/es6-promise/issues"
    },
    "dependencies": {},
    "description": "A lightweight library that provides tools for organizing asynchronous code",
    "devDependencies": {
        "broccoli-babel-transpiler": "^5.6.1",
        "broccoli-concat": "^3.1.0",
        "broccoli-merge-trees": "^1.2.3",
        "broccoli-rollup": "^1.0.2",
        "broccoli-stew": "^1.2.0",
        "broccoli-uglify-js": "^0.2.0",
        "broccoli-watchify": "^1.0.1",
        "ember-cli": "2.12.0-beta.1",
        "ember-cli-dependency-checker": "^1.3.0",
        "ember-publisher": "0.0.7",
        "git-repo-version": "0.4.1",
        "json3": "^3.3.2",
        "mocha": "^3.1.0",
        "promises-aplus-tests-phantom": "^2.1.0-revise",
        "release-it": "2.6.0"
    },
    "directories": {
        "lib": "lib"
    },
    "dist": {
        "shasum": "dda03ca8f9f89bc597e689842929de7ba8cebdf0",
        "tarball": "https://registry.npmjs.org/es6-promise/-/es6-promise-4.1.0.tgz"
    },
    "files": [
        "dist",
        "lib",
        "es6-promise.d.ts",
        "auto.js",
        "!dist/test"
    ],
    "gitHead": "b2f10f231cf8ab195275c489ab4c9653bf023843",
    "homepage": "https://github.com/stefanpenner/es6-promise#readme",
    "keywords": [
        "promises",
        "futures"
    ],
    "license": "MIT",
    "main": "dist/es6-promise.js",
    "maintainers": [
        {
            "name": "jaffathecake"
        },
        {
            "name": "stefanpenner"
        }
    ],
    "name": "es6-promise",
    "namespace": "es6-promise",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/stefanpenner/es6-promise.git"
    },
    "scripts": {
        "build": "ember build --environment production",
        "build:production": "ember build --env production",
        "dry-run-release": "ember build --environment production && release-it --dry-run --non-interactive",
        "lint": "jshint lib",
        "prepublish": "ember build --environment production",
        "start": "ember s",
        "test": "ember test",
        "test:node": "ember build && mocha ./dist/test/browserify",
        "test:server": "ember test --server"
    },
    "spm": {
        "main": "dist/es6-promise.js"
    },
    "typings": "es6-promise.d.ts",
    "version": "4.1.0",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
