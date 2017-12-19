---
title: "@rappopo/dab-memory"
date: 2017-12-19T09:33:22+07:00
weight: 100
draft: false
---

A DAB implementation for in-memory datastore, powered by [Lodash](https://lodash.com/) and [lodash-query](https://github.com/kenansulayman/lodash-query).

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-memory
```

And within your script:

```javascript
const DabMemory = require('@rappopo/dab-memory')
const dab = new DabMemory({
  data: [
    ....
  ]
})
...
dab.findOne('my-doc').then(function(doc) { ... })
```

## Options

`data`: your in-memory data as array of objects, with **id** as the primary key. Defaults to empty array. 

Example:

```javascript
data: [
  { id: 'jack-bauer', name: 'Jack Bauer' },
  { id: 'james-bond', name: 'James Bond' }
]
```

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
