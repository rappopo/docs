---
title: "@rappopo/dab-couch"
date: 2017-12-19T09:24:46+07:00
weight: 150
draft: false
---

A DAB implementation for CouchDB 2.0 and above.

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-couch
```

And within your script:

```javascript
const DabCouch = require('@rappopo/dab-couch')
const dab = new DabCouch({
  url: 'http://localhost:5984',
  dbName: 'mydb'
})
...
dab.findOne('my-doc').then(function(doc) { ... })
```

## Options

`url`: your CouchDB url endpoint. If it not provided, it defauts to: *http://localhost:5984*

`dbName`: the database name to connect to. Defaults to *test*

`retainOnRemove`: array of columns to retain when a document is deleted. Default: []. 

When CouchDB delete a document, it actually PUTs a document with content like this:

```javascript
{
  "_id": "<doc_id>",
  "_rev": "<rev_id>",
  "_deleted": true
}
```

But sometimes you want to also have some columns to be put on that deleted document. The `retainOnRemove` simply left those columns intact, e.g:

```javascript
{
  "_id": "<doc_id>",
  "_rev": "<rev_id>",   
  "_deleted": true,
  "type": "ADDRESS"
}
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
