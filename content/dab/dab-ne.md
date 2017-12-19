---
title: "@rappopo/dab-ne"
date: 2017-12-19T09:33:32+07:00
weight: 110
draft: false
---

A DAB implementation for NeDB. 

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-ne
```

And within your script:

```javascript
const DabNe = require('@rappopo/dab-ne')
const dab = new DabNe({
  path: '/path/to/nedb',
  dbName: 'mydb'
})
...
dab.findOne('my-doc').then(function(doc) { ... })
```

## Options

`path`: the path where all NeDB files will be saved and reside. If it not provided, it'll defaults to */tmp*

`dbName`: the database name. You'll most likely want to give a custom name, otherwise it defaults to *test*

`inMemory`: if it *true*, data won't be persisted. Defaults to *false* 

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
