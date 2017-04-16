# api documentation for  [blocked (v1.2.1)](https://github.com/visionmedia/node-blocked#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-blocked.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-blocked) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-blocked.svg)](https://travis-ci.org/npmdoc/node-npmdoc-blocked)
#### check if the event loop is blocked

[![NPM](https://nodei.co/npm/blocked.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/blocked)

[![apidoc](https://npmdoc.github.io/node-npmdoc-blocked/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-blocked/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-blocked/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-blocked/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/visionmedia/node-blocked/issues"
    },
    "dependencies": {},
    "description": "check if the event loop is blocked",
    "devDependencies": {
        "istanbul": "0.4.1",
        "mocha": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "e22efe767863c65ab8197f6252929104e1ec9ce2",
        "tarball": "https://registry.npmjs.org/blocked/-/blocked-1.2.1.tgz"
    },
    "engines": {
        "node": ">= 0.9.1"
    },
    "gitHead": "530ab392d549b3a1284c949aff6d20e43a0ddcbc",
    "homepage": "https://github.com/visionmedia/node-blocked#readme",
    "keywords": [
        "block",
        "event",
        "loop",
        "performance"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "ensonik"
        },
        {
            "name": "juliangruber"
        },
        {
            "name": "tjholowaychuk"
        }
    ],
    "name": "blocked",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/visionmedia/node-blocked.git"
    },
    "scripts": {
        "coverage": "./node_modules/istanbul/lib/cli.js cover node_modules/mocha/bin/_mocha -- 'test.js'",
        "test": "./node_modules/mocha/bin/mocha"
    },
    "version": "1.2.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module blocked](#apidoc.module.blocked)
1.  [function <span class="apidocSignatureSpan"></span>blocked (fn, options)](#apidoc.element.blocked.blocked)
1.  [function <span class="apidocSignatureSpan">blocked.</span>toString ()](#apidoc.element.blocked.toString)



# <a name="apidoc.module.blocked"></a>[module blocked](#apidoc.module.blocked)

#### <a name="apidoc.element.blocked.blocked"></a>[function <span class="apidocSignatureSpan"></span>blocked (fn, options)](#apidoc.element.blocked.blocked)
- description and source-code
```javascript
blocked = function (fn, options) {
    var opts = options || {};
    var start = process.hrtime();
    var interval = 100;
    var threshold = opts.threshold || 10;

    return setInterval(function () {
        var delta = process.hrtime(start);
        var nanosec = delta[0] * 1e9 + delta[1];
        var ms = nanosec / 1e6;
        var n = ms - interval;

        if (n > threshold) {
            fn(Math.round(n));
        }
        start = process.hrtime();
    }, interval).unref();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.blocked.toString"></a>[function <span class="apidocSignatureSpan">blocked.</span>toString ()](#apidoc.element.blocked.toString)
- description and source-code
```javascript
toString = function () {
    return toString;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
