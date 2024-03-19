---
title: Postgres driver
type: docs
prev: /drivers
next: docs/drivers
---

The Postgres driver is a library that enables DBCaml to talk to Postgres databases, it works as a bridge between the library and the database.

## Installation

```bash
opam pin dbcaml_driver_postgres.0.0.1 git+https://github.com/dbcaml/dbcaml
```

## Usage

```ocaml
  let driver =
    Dbcaml_driver_postgres.connection
      "postgresql://postgres:mysecretpassword@localhost:6432/development"
  in
```
