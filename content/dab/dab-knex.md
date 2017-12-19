---
title: "@rappopo/dab-knex"
date: 2017-12-19T09:33:17+07:00
weight: 130
draft: false
---

A DAB implementation for [Knex](http://knexjs.org/)

## Installation

Simply invoke this command in your project folder:

```
$ npm install --save @rappopo/dab-knex
```

Don't forget to also install the needed client library, e.g (if you choose to use sqlite3):

```
$ npm install sqlite3
```

And within your script:

```javascript
const DabKnex = require('@rappopo/dab-knex')
const dab = new DabKnex({
  client: 'sqlite3',
  connection: {
    filename: '/tmp/mydb.sqlite3'
  },
  table: 'mytable'
})
...
dab.findOne('my-doc', { table: 'othertable' }).then(function(doc) { ... })
```

## Options

`client`: your Knex's client database library

`connection`: your Knex's connection settings

`table`: the default table to use. If you don't provide the table in method's params explicitly, this one will be used. Optional, defauts to *test*

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
