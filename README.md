# firebase-cookie-session

[![NPM Version][npm-image]][npm-url]
[![NPM Downloads][downloads-image]][downloads-url]
[![Build Status][travis-image]][travis-url]
[![Test Coverage][coveralls-image]][coveralls-url]
[![Gratipay][gratipay-image]][gratipay-url]

Simple cookie-based session middleware designed to work with Firebase Cloud Functions.

On Firebase Cloud Functions, only the specially-named `__session` cookie is permitted to pass through to the function execution.

This module is forked from [`express/cookie-session`](https://github.com/express/cookie-session), but behaves differently in
how it stores the cookie signature to ensure that both the value and signature of the session are stored in `__session`.

## Install

```shs
$ npm install firebase-cookie-session --save
```

## API

```js
var cookieSession = require('cookie-session')
var express = require('express')

var app = express()

app.use(cookieSession({
  keys: [/* secret keys */],

  // Cookie Options
  maxAge: 24 * 60 * 60 * 1000 // 24 hours
}))
```
