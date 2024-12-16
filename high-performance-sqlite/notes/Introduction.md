
## What is SQLite?

SQLite is a relational database, very much similar to MySQL or Postgres.

In the case of something like MySQL or Postgres, there is a database server, and a database client that are communicating with each other over some form of protocol (a typical client-server model).

SQLite doesn't follow the client-server model. It is actually a C library that just directly talks to the database file stored on the disk. There is no such thing as a server to monitor or recover.

The configuration is way simpler with SQLite in relation to MySQL or Postgres.

In the case of SQLite, a database is usually just a single file. Under the hood, the C library works with this single file. This is great because it makes it extremely, extremely portable!

```
Fun Fact: SQLite is actually the archival format used by the Library of Congress of the United States!
```


