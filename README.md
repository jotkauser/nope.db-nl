<img src="https://i.ibb.co/C1vZ1j9/nope-db.png" alt="nope.db" />

[![nope.db](https://img.shields.io/badge/nope-db-red.svg)](https://www.npmjs.org/package/nope.db-nl)
[![npm version](https://img.shields.io/npm/v/nope.db.svg?style=flat-square)](https://www.npmjs.org/package/nope.db-nl)
[![install size](https://packagephobia.now.sh/badge?p=nope.db)](https://packagephobia.now.sh/result?p=nope.db-nl)
[![npm downloads](https://img.shields.io/npm/dm/nope.db.svg?style=flat-square)](http://npm-stat.com/charts.html?package=nope.db-nl)
[![GitHub License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/jotkauser/nope.db-nl/blob/0.0.9/LICENSE)
[![Discord](https://img.shields.io/discord/747043879726874734?color=%237289DA&label=Discord)](https://discord.gg/trDF8fb)

> Simple, convenient JSON database for nodejs.

Version 1.0.1, added .splice() STILL BUGGY. DON'T USE IN PRODUCTION PROJECTS
<hr>

# Getting Started

Installing the npm package
```console
$ npm install nope.db
```
Usage of nope.db
```js
const nopedb = require("nope.db");
const db = new nopedb({
    path: "./path/of/database.json",
    seperator: ".",
    spaces: 2
});
```

<hr>

# Documentation

- [Getting Started](#getting-started)
- [Documentation](#documentation)
  - [new nopeDB(settings)](#new-nopedbsettings)
  - [Methods](#methods)
    - [add(id, value)](#addid-value)
    - [all()](#all)
    - [clear(id)](#clearid)
    - [delete(id)](#deleteid)
    - [get(id)](#getid)
    - [has(id)](#hasid)
    - [push(id, value)](#pushid-value)
    - [set(id, value)](#setid-value)
    - [subtract(id, value)](#subtractid-value)
  - [DatabaseError](#databaseerror)
## new nopeDB(settings)
<div class="nopeDB"></div>

Creates or gets a database file
- **Params:**
  - **settings** - An object with the settings
    - **settings.path** - The path of the database (must be an absolute path / the folder should be created) 
    - **settings.seperator** - Seperator for the ID's
    - **settings.spaces** - The spaces of the database file
- **Throws:** [DatabaseError()](#DatabaseError) - If there are no settings or any settings are invalid

## Methods

### add(id, value)
Adds the value of an element in the database
- **Params:**
  - **id** - The ID of the element
  - **value** - The value to be added
- **Returns:** **Number** - Result
- **Throws:** [DatabaseError()](#DatabaseError) - If the ID or value is invalid

### all()
Return the all data on the database
- **Returns:** **Object** - The all data

### clear(id)
Deletes all the data in database / [.reset()](#reset) method is same
- **Returns:** **true** - Indicates that it was cleared

### delete(id)
Deletes element from database / [.remove()](#remove) method is same
- **Params:**
  - **id** - The ID of the element
- **Returns:** **Boolean** - Indicates that it was deleted
- **Throws:** [DatabaseError()](#DatabaseError) - If the ID is invalid

### get(id)
Gets the element on the database / [.fetch()](#fetch) method is same
- **Params:**
  - **id** - The ID of the element
- **Returns:** * - The data
- **Throws:** [DatabaseError()](#DatabaseError) - If the ID is invalid

### has(id)
Checks for data in the database
- **Params:**
  - **id** - The ID of the element
- **Returns:** **Boolean** - Indicates presence
- **Throws:** [DatabaseError()](#DatabaseError) - If the ID is invalid

### push(id, value)
Pushs the data in a array from database
- **Params:**
  - **id** - The ID of the element
  - **value** - The pushed element
- **Returns:** **Array** - The array of the ID
- **Throws:** [DatabaseError()](#DatabaseError) - If the ID or value is invalid

### set(id, value)
Sets the value of an element in the database
- **Params:**
  - **id** - The ID of the element
  - **value** - The value to be setted
- **Returns:** * - The value setted
- **Throws:** [DatabaseError()](#DatabaseError) - If the ID or value is invalid

### subtract(id, value)
Subtracts the value of an element in the database
- **Params:**
  - **id** - The ID of the element
  - **value** - The value to be subtract
- **Returns:** **Number** - Result
- **Throws:** [DatabaseError()](#DatabaseError) - If the ID or value is invalid
- 

## DatabaseError
<div class="DatabaseError"></div>

Extends [Error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error), only used for error reference