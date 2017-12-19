---
title: "@rappopo/dab-mongo"
date: 2017-12-19T09:33:27+07:00
weight: 120
draft: false
---

A DAB implementation for MongoDB. 

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-mongo
```

And within your script:

```javascript
const DabMongo = require('@rappopo/dab-mongo')
const dab = new DabMongo({
  url: 'mongodb://localhost:27017/mydb',
  collection: 'docs'
})
...
dab.findOne('my-doc').then(function(doc) { ... })
```

## Options

`url`: your MongoDB url endpoint. If it not provided, it defauts to: *mongodb://localhost:27017/test*

`collection`: the collection name. You'll most likely want to give a custom name, otherwise it defaults to *docs*

## Methods

* [x] [find](/dab/method/find/)
* [x] [findOne](/dab/method/find-one/)
* [x] [create](/dab/method/create/)
* [x] [update](/dab/method/update/)
* [x] [remove](/dab/method/remove/)
* [x] [bulkCreate](/dab/method/bulk-create/)
* [x] [bulkUpdate](/dab/method/bulk-update/)
* [x] [bulkRemove](/dab/method/bulk-remove/)
* [x] [copyFrom](/dab/method/copy-from/)
* [x] [copyTo](/dab/method/copy-to/)
