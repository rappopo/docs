---
title: "copyFrom"
date: 2017-12-18T13:38:42+07:00
draft: false
weight: 90
---

> **copyFrom (source, params)**

This method gives you a full power of document imports.

## Arguments
### Source (mixed, required)

If source is a json file, than all contained documents will be inserted to the database, e.g:

```javascript
...
dab.copyFrom('/path/of/my/file.json').then(function (result) { ... })
...
```

But if source is another DAB instance, then it will be queried and copied over as chunks. E.g:

```javascript
var source = new DabCouch({ ... }),
  dab = new DabMemory()

dab.copyFrom(source, {
  query: {
    age: {
      $gt: 20
    }
  },
  limit: 10
}).then(function (result) { ... })
```

### Params (optional)

`query`: query target datasource, optional, defaults to `{}`. Ignored if source is a filename.

`limit`: max. number of rows per page/chunk. Optional, defaults to 25. This is NOT the max. rows you're gonna get. You'll always get ALL rows matched with your query. It is here to limit the query results so it won't crash your server. The higher you put the limit, the faster to get things done. But it'll also introduce more danger as your server will consume much more memories.

`withDetail`: if *true*, like in all bulk methods, result will carry the detail of every transaction. Default: *false*

## Response

Method should always return a response, eventhough one or more insertion could fail. If failed, those corresponding rows should tell why it failed, if enabled through `withDetail` parameter above. 

Promise rejection error should only occour when something very bad happened within the script.

Example:

```javascript
{
  success: true,
  stat: {
    ok: 2,
    fail: 1,
    total: 3
  },
  detail: [
    { _id: 'james-bond', success: false, message: 'Exists' },
    { _id: 'jack-bauer', success: true },
    { _id: '337b116d-650e-4581-8bef-7b119467b05c', success: true }
  ]
}
```

