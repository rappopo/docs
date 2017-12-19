---
title: "@rappopo/dab-es"
date: 2017-12-19T09:33:12+07:00
weight: 160
draft: false
---

A DAB implementation for Elasticsearch. The excellent library [e3po](https://github.com/dab00/e3po) is used to transform Mongo Query Language to Elasticsearch DSB.

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-es
```

And within your script:

```javascript
const DabEs = require('@rappopo/dab-es')
const dab = new DabEs({
  hosts: ['localhost:9200'],
  index: 'myindex',
  type: 'mytype'
})
...
dab.findOne('my-doc').then(function(doc) { ... })
```

## Options

`hosts`: your Elasticsearch hosts array. If it not provided, it defauts to: *['localhost:9200']*

`index`: the index name to bound to. Defaults to *test*

`type`: the default type use. Defaults to *doc*

Index and/or type can also be provided as params during a method call. If you do this, the provided one will be used instead.

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
