
# LowlaDB-Node-Mongo [![Build Status](https://travis-ci.org/lowla/lowladb-node-mongo.svg)](https://travis-ci.org/lowla/lowladb-node-mongo)

> A MongoDB Datastore for LowlaDB on Node servers.

## Installation ##

```bash
$ npm install lowladb-node-mongo --save
```

## Usage ##

Construct an instance of MongoDatastore and configure LowlaDB to use it instead of the default datastore.

```js
var app = require('express');
var lowla = require('lowladb-node');
var MongoDatastore = require('lowladb-node-mongo');

var lowlaConfig = {
  datastore: new MongoDatastore({ mongoUrl: 'mongodb://127.0.0.1/lowladb' })
};

lowla.configureRoutes(app, lowlaConfig);
```

The `MongoDatastore` constructor takes an optional configuration object.  The following options are supported:

```js
{
  // A MongoDB database to use, or falsey to use mongoUrl below instead
  db: false,

  // The Mongo URL to connect to if db was not specified
  mongoUrl: 'mongodb://127.0.0.1/lowladb',

  // Where to send log output
  logger: console
}
```
