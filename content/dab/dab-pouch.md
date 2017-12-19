---
title: "@rappopo/dab-pouch"
date: 2017-12-19T09:33:38+07:00
weight: 140
draft: false
---

A DAB implementation for PouchDB.

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-pouch
```

And within your script:

```javascript
const DabPouch = require('@rappopo/dab-pouch')
const dab = new DabPouch({
  path: '/home/me/pouchdb',
  dbName: 'mydb'
})
...
dab.findOne('my-doc').then(function(doc) { ... })
```

## Options

`path`: the path where all PouchDB folder will be saved and reside. If it not provided, it'll defaults to */tmp*

`dbName`: the database name. You'll most likely want to give a custom name, otherwise it defaults to *test*

`retainOnRemove`: array of columns to retain when a document is deleted. Default: []. 

When PouchDB delete a document, it actually PUTs a document with content like this:

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
  "type": "<mytype>"
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
