---
title: Drivers
next-page: postgres
---

The driver is responsible for communicating with the database. It acts as a bridge between DBCaml and the database. The main idea behind having separate drivers as a library is to avoid the need for installing unnecessary libraries. For example, if you are working with a Postgres database, there is no need to install any MySQL drivers. By keeping the drivers separate, unnecessary dependencies can be avoided.

Additionally, the driver takes care of all the security measures within the library. DBCaml simply provides the necessary data to the drivers, which handle the security aspects.

