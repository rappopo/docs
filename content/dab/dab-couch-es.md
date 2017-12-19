---
title: "@rappopo/dab-couch-es"
date: 2017-12-19T10:21:48+07:00
weight: 170
draft: false
---

A DAB implementation for CouchDB 2.0 AND Elasticsearch for finding documents. 

You might ask yourself, why this useless package if there are already [@rappopo/dab-couch](https://github.com/rappopo/dab-couch) and [@rappopo/dab-es](https://github.com/rappopo/dab-es)? Well, this package is a thin wrapper around those two. Only the `find` method is taken from @rappopo/dab-es, while the rest are from @rappopo/dab-couch.

I make this stupid package because I work alot with both CouchDB and Elasticsearch. Both systems are connected to each other through [@rappopo/nesu](https://github.com/rappopo/nesu) in the back, which basically listen to CouchDB changes stream and forward it to Elasticsearch for indexing.

So whenever I create/update/delete document on CouchDB, it will be ready for querying in Elasticsearch. Perfecto! Right? Or, ... emh... still pretty stupid isn't it ??

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-couch-es
```

And within your script:

```javascript
const DabCouchEs = require('@rappopo/dab-couch-es')
const dab = new DabCouchEs({
  couch: {
    url: 'http://localhost:5984',
    dbName: 'mydb'    
  },
  es: {
    hosts: ['localhost:9200'],
    index: 'myindex',
    type: 'mytype'
  },
  delay: 1000
})
...
dab.findOne('my-doc').then(function(doc) { ... })
```

## Options

`couch`: see [@rappopo/dab-couch](https://github.com/rappopo/dab-couch) options

`es`: see [@rappopo/dab-es](https://github.com/rappopo/dab-es) options

`delay`: time to wait (in ms) to let CouchDB fully synchronize with Elasticsearch after a create/update/remove action. Optional, defaults to 1000 ms

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
