The file `test.js` runs an assertion `assert.rejects( () => Promise.reject() );` which passes in node.js.

using `npm run pack` webpack bundles this code into `test.bundle.js`. When run from node (or e.g. in a browser) it produces the following output. Why?

```bash
npm test

> webpackery@1.0.0 test /Users/andrewgibson/src/webpackery
> node test.js && node test.bundle.js

webpack:///./test.js?:2
assert.rejects( () => Promise.reject() );
       ^

TypeError: assert.rejects is not a function
    at eval (webpack:///./test.js?:2:8)
    at Object../test.js (/Users/andrewgibson/src/webpackery/test.bundle.js:175:1)
    at __webpack_require__ (/Users/andrewgibson/src/webpackery/test.bundle.js:20:30)
    at /Users/andrewgibson/src/webpackery/test.bundle.js:84:18
    at Object.<anonymous> (/Users/andrewgibson/src/webpackery/test.bundle.js:87:10)
    at Module._compile (internal/modules/cjs/loader.js:774:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:785:10)
    at Module.load (internal/modules/cjs/loader.js:641:32)
    at Function.Module._load (internal/modules/cjs/loader.js:556:12)
    at Function.Module.runMain (internal/modules/cjs/loader.js:837:10)
```

