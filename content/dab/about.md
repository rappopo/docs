---
title: "About"
date: 2017-12-18T10:14:47+07:00
draft: false
weight: 10
---

{{% notice warning %}}
All of these are for dummies only!!! If you're considered yourself as a kungfu master, than you'd probably better to look for masterpieces like [Waterline](https://github.com/balderdashy/waterline) or [Sequelize](https://github.com/sequelize/sequelize) instead!!! But if you're a dummy like me, then welcome to the party! Yay!! Finally a database access for fools!!! With lots of stuff and magic!!!!
{{% /notice %}}

## Background

Rappopo DAB is a set of conventions of database abstraction layer with focus on how to access and work with data easily. It won't be a very sophisticated and overly complex library. On the contrary, it'll only support the most basic operations. Not because we don't need it, but simply because I'm too stupid & lazy to write one :)

In my work as a lousy programmer right now, I have to work with many different database. Be it relational or NoSQL. And through all the times, I have to face the same problem over and over again: different ways to access the data, learning it's query language, and so on. The list grows very quickly.

That's why this project is born. It should helps lazy and stupid people like me to get more time to drink beer. Not learning a new alien language over-and-over again.

Existing libraries are way to complex for me. I only need the most basic ones: queryable through MongoDB-like query language, pagination mechanism. And simple import & export data. I also a true fan of RESTful APIs, so why don't I blindly copy their way to get, create, update & remove records? No more learning! More time for beer!! 

## Usage

**For developers**: this package gives you a basic class and guide lines on how to write package for some particular database. All you need to do is just extends this basic class and write methods according to its specification.

**For end user**: never use this package directly, because it won't gives you anything other than useless stuffs! Instead, pick one of its [implementation library](/dab/implementation/) below that match the database you're currently working with.

If for some reason you want to change the database later, the only thing you need to do is just requiring a different library and put its options correctly. Everything else should be the same.

Example (development):

```javascript
var Dab = require('@rappopo/dab-ne'),
  dab = new Dab({ dbName: 'mydb' })

dab.find().then(function (results) => { ... })
```

And later in production, just change to this:

```javascript
var Dab = require('@rappopo/dab-couch'),
  dab = new Dab({ url: 'http://localhost:5984', dbName: 'mydb' })

// everything below this line should still be the same
dab.find().then(function (results) => { ... })
```
