❕ Not official adonis shield repo. Only use this package when you need adonis shield without cookies.

# Adonis Shield wihout session (v4 only)🛡️

Adonis shield is middleware to standard HTTP websites to protect themselves from common web attacks like **xss** and **csp**.

[![NPM Version][npm-image]][npm-url]

NOTE: You don't need this middleware if you are writing an API server.

## Difference between this package and official

This package don't use session provider. 

CSRF protection has been disabled as it requires the use of cookies.

## Installation 

```
adonis install adonis-shield-no-session
```

## What's in the box?

1. Support to define [CSP policies](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP).
2. Setup [X-Content-Type-Options](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Content-Type-Options) header.
3. Setup [X-Frame-Options](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options) header.
4. Setup [X-XSS-Protection](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection) header.


## Setup
Checkout [instructions](instructions.md) file on how to setup this inside Adonisjs application.

## Node/OS Target

This repo/branch is supposed to run fine on all major OS platforms and targets `Node.js >=7.0`

## Development

Great! If you are planning to contribute to the framework, make sure to adhere to following conventions, since a consistent code-base is always joy to work with.

Run the following command to see list of available npm scripts.

```
npm run
```

### Tests & Linting

1. Lint your code using standardJs. Run `npm run lint` command to check if there are any linting errors.
2. Make sure you write tests for all the changes/bug fixes.
3. Also you can write **regression tests**, which shows that something is failing but doesn't breaks the build. Which is actually a nice way to show that something fails. Regression tests are written using `test.failing()` method.
4. Make sure all the tests are passing on `travis` and `appveyor`.

### General Practices

Since Es6 is in, you should strive to use latest features. For example:

1. Use `Spread` over `arguments` keyword.
2. Never use `bind` or `call`. After calling these methods, we cannot guarantee the scope of any methods and in AdonisJs codebase we do not override the methods scope.
3. Make sure to write proper docblock.

## Issues & PR

It is always helpful if we try to follow certain practices when creating issues or PR's, since it will save everyone's time.

1. Always try creating regression tests when you find a bug (if possible).
2. Share some context on what you are trying to do, with enough code to reproduce the issue.
3. For general questions, please create a forum thread.
4. When creating a PR for a feature, make sure to create a parallel PR for docs too.


## Regression Tests

Regression tests are tests, which shows how a piece of code fails under certain circumstance, but the beauty is even after the failure, the test suite will never fail. Actually is a nice way to notify about bugs, but making sure everything is green.

The regression tests are created using

```
test.failing('2 + 2 is always 4, but add method returns 6', (assert) => {
 assert.true(add(2, 2), 4)
})
```

Now since the `add` method has a bug, it will return `6` instead of `4`. But the build will pass.

[npm-image]: https://img.shields.io/npm/v/adonis-shield-no-session

[npm-url]: https://www.npmjs.com/package/adonis-shield-no-session
