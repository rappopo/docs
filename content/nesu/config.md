---
title: "Configuration"
date: 2017-12-18T14:17:51+07:00
draft: false
weight: 20
---

You need to create/edit the configuration file *config.js* in the same folder as your bootstrap file. Please see the example above.

### Main Entries

`db.<mydb>.<prop>`: put your database info here. `<mydb>` is the name of CouchDB database you want to stream to Elasticsearch. Put as many databases you want here, **Nesu** will stream all away.

`default.<prop>`: serve as default properties. Will be used if none are provided in `db.<mydb>.<prop>` section.

### Properties

`bulkLimit`: max. number of documents in a bulk operation. Optional, defaults to 1000 documents

`idleTimeout`: how long to wait for a new changes to arrive. In seconds, optional, default to 2 seconds. If you put 0 in it, it'll use continuous stream provided by *nano.db.follow* instead of regular polling (*nano.db.changes*)

`cdb.url`: the url of your CouchDB server endpoint. Optional, defaults to http://localhost:5984

`cdb.name`: name of CouchDB database if different from the db's key name. Optional, defaults to the db's key

`es.url`: the url of your Elasticsearch endpoint. Optional, defaults to http://localhost:9200

`es.name`: name of Elasticsearch index if different from the db's key name. Optional, defaults to the db's key

`es.typeField`: document's key name to be used as Elasticsearch's type field. Optional, defaults to **doc**. 

## Transformer

You have the ability to transform each document to something new before written to Elasticsearch easily. 

All you need to do is just create a new js file inside the *transformer* folder with the exact name as its corresponding database. E.g. if your database name is *mydb*, than your transformer file will be *mydb.js*

And use the following code fragment as your start:

```javascript
module.exports = function(doc, callback) {
  .....
  callback(doc)
}
```

## Last Sequence

Everytime a bulk of documents is written to Elasticsearch, its last sequence is saved in a file named after the database name, inside *last_seq* folder.

To reset the sequence from the very beginning, just delete the file. To start from an exact known sequence, just override its content. And to start from the actual one, put 'now' (without the quotes) in it
