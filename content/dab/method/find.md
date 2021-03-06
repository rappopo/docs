---
title: "find"
date: 2017-12-18T13:37:03+07:00
draft: false
weight: 10
---

> **find (params)**

Query specific document from selected database using MongoDB-like query language. 

## Arguments
### Params (optional)

As parameter, pass the following object:

* `query`: query in MongoDB-style query syntax. Optional, defaults to: `{}` (match all).
* `sort`: sort order, as an array of object. Optional. Example:

    ```javascript
    [{ name: 'asc', age: 'desc' }]
    ```

* `limit`: max. number of documents in one page. Optional, default: `25`. Overrideable through [options](OPTIONS.md) object.
* `page`: page number, starting from 1. Optional, defaults: 1

Example:

```javascript
{
  query: {
    age: { $gt: 20 }
  },
  page: 1,
  limit: 25
}
```

## Response

It should return object according to this schema:

```javascript
{
  success: true,
  total: 120,
  data: [
    { id: 'james-bond', name: 'James Bond', age: 20 },
    { id: 'jack-bauer', name: 'Jack Bauer', age: 20 },
    { id: 'jason-bourne', name: 'Jason Bourne', age: 20 },
    ...
  ]
}
```

If no document found, it should **NOT** yield error. Instead, it sould return an empty data with total = 0.

`total` is the total number of documents found matched with your query. Optional, but strongly recommended to return this value.
