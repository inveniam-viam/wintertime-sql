## SQLite is just a file!

A SQLite database is just a file on disk, which is very different from MySQL or Postgres.

A SQLite database file has a very, very strictly-defined format. It has great backwards compatibility. It is also extremely cross-platform.

If you put all of your data in a SQLite file, the odds that any computing platform will be able to read that file is almost 100%.

### Use Case

If you put your file in a SQLite file, you can distribute it very easily.

You can easily send this file out to any type of client (mobile or desktop or front-end or other servers); it is a nice data packaging format!

Storing a database in a SQLite file means you will have guaranteed backwards compatibility!

Finally, there is zero over head when it comes to creating a SQLite database. Every database is just a file.

Having a low overhead file-based approach makes it very easy to run tests. Instead of having to run MySQL locally / CI-CD / in production, you just have one single file to deal with when using SQLite.
