# api documentation for  [local-links (v1.4.1)](https://github.com/lukekarrys/local-links)  [![npm package](https://img.shields.io/npm/v/npmdoc-local-links.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-local-links) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-local-links.svg)](https://travis-ci.org/npmdoc/node-npmdoc-local-links)
#### Determine cross-browser if an event or anchor element should be handled locally.

[![NPM](https://nodei.co/npm/local-links.png?downloads=true)](https://www.npmjs.com/package/local-links)

[![apidoc](https://npmdoc.github.io/node-npmdoc-local-links/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-local-links_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-local-links/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-local-links/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-local-links/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Luke Karrys",
        "email": "luke@lukekarrys.com"
    },
    "bugs": {
        "url": "https://github.com/lukekarrys/local-links/issues"
    },
    "dependencies": {},
    "description": "Determine cross-browser if an event or anchor element should be handled locally.",
    "devDependencies": {
        "browserify": "^13.1.0",
        "electron-prebuilt": "^1.3.2",
        "git-validate": "^2.1.4",
        "jquery": "^3.1.0",
        "lodash.partial": "^4.2.0",
        "run-browser": "^2.0.2",
        "standard": "^8.0.0-beta.3",
        "tap-spec": "^4.1.1",
        "tape": "^4.6.0",
        "tape-run": "^2.1.4",
        "zuul": "^3.10.3",
        "zuul-ngrok": "^4.0.0"
    },
    "directories": {},
    "dist": {
        "shasum": "bfc94f3d09cc444f0d14408f80f9c59292c57e35",
        "tarball": "https://registry.npmjs.org/local-links/-/local-links-1.4.1.tgz"
    },
    "gitHead": "792ba70eb3193b08ae958f21b6e33fb09dfdae13",
    "homepage": "https://github.com/lukekarrys/local-links",
    "keywords": [
        "IE",
        "links",
        "local"
    ],
    "license": "MIT",
    "main": "local-links.js",
    "maintainers": [
        {
            "name": "lukekarrys",
            "email": "luke@lukekarrys.com"
        }
    ],
    "name": "local-links",
    "optionalDependencies": {},
    "pre-commit": [
        "lint",
        "test",
        "validate"
    ],
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/lukekarrys/local-links.git"
    },
    "scripts": {
        "lint": "standard",
        "start": "run-browser test/index.js",
        "start-80": "run-browser test/index.js --port 80",
        "test": "browserify test/index.js | tape-run -b electron | tap-spec",
        "test-travis": "npm test && npm run zuul",
        "validate": "npm ls",
        "zuul": "zuul --ui tape -- test/index.js",
        "zuul-local": "zuul --local 8080 --ui tape -- test/index.js"
    },
    "version": "1.4.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module local-links](#apidoc.module.local-links)
1.  [function <span class="apidocSignatureSpan">local-links.</span>active ()](#apidoc.element.local-links.active)
1.  [function <span class="apidocSignatureSpan">local-links.</span>getLocalHash ()](#apidoc.element.local-links.getLocalHash)
1.  [function <span class="apidocSignatureSpan">local-links.</span>getLocalPathname ()](#apidoc.element.local-links.getLocalPathname)
1.  [function <span class="apidocSignatureSpan">local-links.</span>hash ()](#apidoc.element.local-links.hash)
1.  [function <span class="apidocSignatureSpan">local-links.</span>isActive ()](#apidoc.element.local-links.isActive)
1.  [function <span class="apidocSignatureSpan">local-links.</span>isLocal (event, anchor, lookForHash)](#apidoc.element.local-links.isLocal)
1.  [function <span class="apidocSignatureSpan">local-links.</span>pathname ()](#apidoc.element.local-links.pathname)



# <a name="apidoc.module.local-links"></a>[module local-links](#apidoc.module.local-links)

#### <a name="apidoc.element.local-links.active"></a>[function <span class="apidocSignatureSpan">local-links.</span>active ()](#apidoc.element.local-links.active)
- description and source-code
```javascript
function active() {
  var args = Array.prototype.slice.call(arguments)
  var last = args[args.length - 1]
  var checkPath = window.location.pathname

  if (typeof last === 'string') {
    checkPath = last
    args = args.slice(0, -1)
  }

  return pathname.apply(null, args) === normalizeLeadingSlash(checkPath)
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.local-links.getLocalHash"></a>[function <span class="apidocSignatureSpan">local-links.</span>getLocalHash ()](#apidoc.element.local-links.getLocalHash)
- description and source-code
```javascript
function hash() {
  return isLocal.apply(null, getEventAndAnchor.apply(null, arguments).concat(true))
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.local-links.getLocalPathname"></a>[function <span class="apidocSignatureSpan">local-links.</span>getLocalPathname ()](#apidoc.element.local-links.getLocalPathname)
- description and source-code
```javascript
function pathname() {
  return isLocal.apply(null, getEventAndAnchor.apply(null, arguments))
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.local-links.hash"></a>[function <span class="apidocSignatureSpan">local-links.</span>hash ()](#apidoc.element.local-links.hash)
- description and source-code
```javascript
function hash() {
  return isLocal.apply(null, getEventAndAnchor.apply(null, arguments).concat(true))
}
```
- example usage
```shell
...
// if the link is local, otherwise it will return null
local.pathname(document.getElementById('local')) // '/page2'
local.pathname(document.getElementById('hash')) // null
local.pathname(document.getElementById('google')) // null

// 'hash()' will return the hash as a string
// if the hash is to this page, otherwise it will return null
local.hash(document.getElementById('local')) // null
local.hash(document.getElementById('hash')) // '#hash'
local.hash(document.getElementById('google')) // null
'''


## API
...
```

#### <a name="apidoc.element.local-links.isActive"></a>[function <span class="apidocSignatureSpan">local-links.</span>isActive ()](#apidoc.element.local-links.isActive)
- description and source-code
```javascript
function active() {
  var args = Array.prototype.slice.call(arguments)
  var last = args[args.length - 1]
  var checkPath = window.location.pathname

  if (typeof last === 'string') {
    checkPath = last
    args = args.slice(0, -1)
  }

  return pathname.apply(null, args) === normalizeLeadingSlash(checkPath)
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.local-links.isLocal"></a>[function <span class="apidocSignatureSpan">local-links.</span>isLocal (event, anchor, lookForHash)](#apidoc.element.local-links.isLocal)
- description and source-code
```javascript
function isLocal(event, anchor, lookForHash) {
  event || (event = {})

  // Skip modifier events
  if (event.altKey || event.ctrlKey || event.metaKey || event.shiftKey) {
    return null
  }

  // Skip non-primary clicks
  if (isSecondaryButton(event)) {
    return null
  }

  // If we have an anchor but its not an A tag
  // try to find the closest one
  if (anchor && !isA(anchor)) {
    anchor = closestA(anchor)
  }

  // Only test anchor elements
  if (!anchor || !isA(anchor)) {
    return null
  }

  // Dont test anchors with target=_blank
  if (anchor.target === '_blank') {
    return null
  }

  // IE9 doesn't put a leading slash on anchor.pathname [1]
  var aPathname = normalizeLeadingSlash(anchor.pathname)
  var wPathname = normalizeLeadingSlash(window.location.pathname)
  var aHost = anchor.host
  var aPort = anchor.port
  var wHost = window.location.host
  var wPort = window.location.port

  // In some cases, IE will have a blank host property when the href
  // is a relative URL. We can check for relativeness via the achor's
  // href attribute and then set the anchor's host to the window's host.
  if (aHost === '' &&
    'attributes' in anchor &&
    'href' in anchor.attributes &&
    'value' in anchor.attributes.href &&
    isRelativeUrl(anchor.attributes.href.value)) {
    aHost = wHost
  }

  // Some browsers (Chrome 36) return an empty string for anchor.hash
  // even when href="#", so we also check the href
  var aHash = anchor.hash || (anchor.href.indexOf('#') > -1 ? '#' + anchor.href.split('#')[1] : null)
  var inPageHash

  // Window has no port, but anchor has the default port
  if (!wPort && aPort && (aPort === '80' || aPort === '443')) {
    // IE9 sometimes includes the default port (80 or 443) on anchor.host
    // so we append the default port to the window host in this case
    // so they will match for the host equality check [1]
    wHost += ':' + aPort
    aHost += aHost.indexOf(aPort, aHost.length - aPort.length) === -1 ? ':' + aPort : '' // [3]
  }

  // Hosts are the same, its a local link
  if (aHost === wHost) {
    // If everything else is the same
    // and hash exists, then it is an in-page hash [2]
    inPageHash =
      aPathname === wPathname &&
      anchor.search === window.location.search &&
      aHash

    if (lookForHash === true) {
      // If we are looking for the hash then this will
      // only return a truthy value if the link
      // is an *in-page* hash link
      return inPageHash
    } else {
      // If this is an in page hash link
      // then ignore it because we werent looking for hash links
      return inPageHash
        ? null
        : aPathname + (anchor.search || '') + (aHash || '')
    }
  }

  return null
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.local-links.pathname"></a>[function <span class="apidocSignatureSpan">local-links.</span>pathname ()](#apidoc.element.local-links.pathname)
- description and source-code
```javascript
function pathname() {
  return isLocal.apply(null, getEventAndAnchor.apply(null, arguments))
}
```
- example usage
```shell
...
'''

'''js
var local = require('local-links');

// 'pathname()' will return the pathname as a string
// if the link is local, otherwise it will return null
local.pathname(document.getElementById('local')) // '/page2'
local.pathname(document.getElementById('hash')) // null
local.pathname(document.getElementById('google')) // null

// 'hash()' will return the hash as a string
// if the hash is to this page, otherwise it will return null
local.hash(document.getElementById('local')) // null
local.hash(document.getElementById('hash')) // '#hash'
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
