---
title: Methods
type: docs
prev: /
---

This page contains the current methods available to use.

## Start the database connection pool

`start_link` is the method you use to start the database pool. It takes a optional argument `connections` and returns the pool process id(PID). This PID is later on used when you make queries to the database

```
Dbcaml.start_link ~connections:10 driver
```

## `fetch_one`

```ocaml
Dbcaml.fetch_one
       pool_id
       ~params:[Dbcaml.Param.String "1"]
       "select * from users where id = $1"
```

## `fetch_many`

```ocaml
Dbcaml.fetch_many
       pool_id
       ~params:[Dbcaml.Param.String "1"]
       "select * from users where id = $1"
```

## `exec`

```ocaml 
Dbcaml.fetch_many
       pool_id
       ~params:[Dbcaml.Param.String "1"]
       "select * from users where id = $1"

```
