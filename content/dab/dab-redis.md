---
title: "@rappopo/dab-redis"
date: 2017-12-19T09:33:43+07:00
weight: 180
draft: false
---

A DAB implementation for [Redis](https://redis.io). 

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-redis
```

And within your script:

```javascript
const DabRedis = require('@rappopo/dab-redis')
const dab = new DabRedis({
  url: 'redis://myhost:6379',
  ns: 'docs'
})
...
dab.findOne('my-doc').then(function(doc) { ... })
```

## Options

`url`: your Redis url endpoint. If it not provided, it defauts to: *redis://localhost:6379*

`ns`: your namespace. You'll most likely want to give a custom name, otherwise it defaults to *doc*

## Methods

* [ ] [find](/dab/method/find/)
* [x] [findOne](/dab/method/find-one/)
* [x] [create](/dab/method/create/)
* [x] [update](/dab/method/update/)
* [x] [remove](/dab/method/remove/)
* [x] [bulkCreate](/dab/method/bulk-create/)
* [x] [bulkUpdate](/dab/method/bulk-update/)
* [x] [bulkRemove](/dab/method/bulk-remove/)
* [ ] [copyFrom](/dab/method/copy-from/)
* [ ] [copyTo](/dab/method/copy-to/)
