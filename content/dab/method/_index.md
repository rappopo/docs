---
title: "Methods & Features"
date: 2017-12-18T13:36:05+07:00
draft: false
weight: 30
---

All methods should return promises. Still, node's callback style can be used by chaining the promise with `.asCallback(fn)`

Example:

```javascript
...
// promise-way
findOne('my-doc')
.then(function (result) {
  console.log(result)
})
.catch(function (err) {
  console.log(err)
})

// callback-way
findOne('my-doc').asCallback(function (err, result) {
  if (err)
    console.log(err)
  else
    console.log(result)
})
```

## Methods

{{% children showhidden="true" %}}