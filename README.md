# api documentation for  [es6-promise (v4.1.0)](https://github.com/stefanpenner/es6-promise#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-es6-promise.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-es6-promise) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-es6-promise.svg)](https://travis-ci.org/npmdoc/node-npmdoc-es6-promise)
#### A lightweight library that provides tools for organizing asynchronous code

[![NPM](https://nodei.co/npm/es6-promise.png?downloads=true)](https://www.npmjs.com/package/es6-promise)

[![apidoc](https://npmdoc.github.io/node-npmdoc-es6-promise/build/screenCapture.buildNpmdoc.browser.%252Fhome%252Ftravis%252Fbuild%252Fnpmdoc%252Fnode-npmdoc-es6-promise%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-es6-promise/build/apidoc.html)

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
            "name": "jaffathecake",
            "email": "jaffathecake@gmail.com"
        },
        {
            "name": "stefanpenner",
            "email": "stefan.penner@gmail.com"
        }
    ],
    "name": "es6-promise",
    "namespace": "es6-promise",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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
    "version": "4.1.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module es6-promise](#apidoc.module.es6-promise)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>Promise (resolver)](#apidoc.element.es6-promise.Promise)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>_asap (callback, arg)](#apidoc.element.es6-promise._asap)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>_setAsap (asapFn)](#apidoc.element.es6-promise._setAsap)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>_setScheduler (scheduleFn)](#apidoc.element.es6-promise._setScheduler)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>all (entries)](#apidoc.element.es6-promise.all)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>polyfill ()](#apidoc.element.es6-promise.polyfill)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>race (entries)](#apidoc.element.es6-promise.race)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>reject (reason)](#apidoc.element.es6-promise.reject)
1.  [function <span class="apidocSignatureSpan">es6-promise.</span>resolve (object)](#apidoc.element.es6-promise.resolve)



# <a name="apidoc.module.es6-promise"></a>[module es6-promise](#apidoc.module.es6-promise)

#### <a name="apidoc.element.es6-promise.Promise"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>Promise (resolver)](#apidoc.element.es6-promise.Promise)
- description and source-code
```javascript
function Promise(resolver) {
  this[PROMISE_ID] = nextId();
  this._result = this._state = undefined;
  this._subscribers = [];

  if (noop !== resolver) {
    typeof resolver !== 'function' && needsResolver();
    this instanceof Promise ? initializePromise(this, resolver) : needsNew();
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.es6-promise._asap"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>_asap (callback, arg)](#apidoc.element.es6-promise._asap)
- description and source-code
```javascript
function asap(callback, arg) {
  queue[len] = callback;
  queue[len + 1] = arg;
  len += 2;
  if (len === 2) {
    // If len is 2, that means that we need to schedule an async flush.
    // If additional callbacks are queued before the queue is flushed, they
    // will be processed by this flush that we are scheduling.
    if (customSchedulerFn) {
      customSchedulerFn(flush);
    } else {
      scheduleFlush();
    }
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.es6-promise._setAsap"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>_setAsap (asapFn)](#apidoc.element.es6-promise._setAsap)
- description and source-code
```javascript
function setAsap(asapFn) {
  asap = asapFn;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.es6-promise._setScheduler"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>_setScheduler (scheduleFn)](#apidoc.element.es6-promise._setScheduler)
- description and source-code
```javascript
function setScheduler(scheduleFn) {
  customSchedulerFn = scheduleFn;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.es6-promise.all"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>all (entries)](#apidoc.element.es6-promise.all)
- description and source-code
```javascript
function all(entries) {
  return new Enumerator(this, entries).promise;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.es6-promise.polyfill"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>polyfill ()](#apidoc.element.es6-promise.polyfill)
- description and source-code
```javascript
function polyfill() {
    var local = undefined;

    if (typeof global !== 'undefined') {
        local = global;
    } else if (typeof self !== 'undefined') {
        local = self;
    } else {
        try {
            local = Function('return this')();
        } catch (e) {
            throw new Error('polyfill failed because global object is unavailable in this environment');
        }
    }

    var P = local.Promise;

    if (P) {
        var promiseToString = null;
        try {
            promiseToString = Object.prototype.toString.call(P.resolve());
        } catch (e) {
            // silently ignored
        }

        if (promiseToString === '[object Promise]' && !P.cast) {
            return;
        }
    }

    local.Promise = Promise;
}
```
- example usage
```shell
...
'''

## Auto-polyfill

To polyfill the global environment (either in Node or in the browser via CommonJS) use the following code snippet:

'''js
require('es6-promise').polyfill();
'''

Alternatively

'''js
require('es6-promise/auto');
'''
...
```

#### <a name="apidoc.element.es6-promise.race"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>race (entries)](#apidoc.element.es6-promise.race)
- description and source-code
```javascript
function race(entries) {
<span class="apidocCodeCommentSpan">  /*jshint validthis:true */
</span>  var Constructor = this;

  if (!isArray(entries)) {
    return new Constructor(function (_, reject) {
      return reject(new TypeError('You must pass an array to race.'));
    });
  } else {
    return new Constructor(function (resolve, reject) {
      var length = entries.length;
      for (var i = 0; i < length; i++) {
        Constructor.resolve(entries[i]).then(resolve, reject);
      }
    });
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.es6-promise.reject"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>reject (reason)](#apidoc.element.es6-promise.reject)
- description and source-code
```javascript
function reject(reason) {
<span class="apidocCodeCommentSpan">  /*jshint validthis:true */
</span>  var Constructor = this;
  var promise = new Constructor(noop);
  _reject(promise, reason);
  return promise;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.es6-promise.resolve"></a>[function <span class="apidocSignatureSpan">es6-promise.</span>resolve (object)](#apidoc.element.es6-promise.resolve)
- description and source-code
```javascript
function resolve(object) {
<span class="apidocCodeCommentSpan">  /*jshint validthis:true */
</span>  var Constructor = this;

  if (object && typeof object === 'object' && object.constructor === Constructor) {
    return object;
  }

  var promise = new Constructor(noop);
  _resolve(promise, object);
  return promise;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
