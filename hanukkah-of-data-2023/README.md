## Hanukkah of Data 2023: Solved with SQLite

This repository contains my solution to the problems posed in the 2023 version of Noah's Rug (Hanukkah of Data).

I have previously solved this series using a combination of Python and pandas, but this repo contains the solutions to the problem solved using SQLite since I've been exploring the internals of the SQLite implementation for fun.


### Installation

I use a Mac, so I installed SQLite using homebrew by just running:

```
brew install sqlite3
```

Yes, the Mac does come with a default installation of SQLite. However, it doesn't allow for loading extensions.

### Initial Checks

After having installed SQLite locally, I did a little setup and cursory checks through the tables:

```
sqlite3 noahs.sqlite
```

Taking a look at the DB configuration:
```
.dbconfig
```

Output:
```
sqlite> .dbconfig
          defensive on
            dqs_ddl off
            dqs_dml off
        enable_fkey off
        enable_qpsg off
     enable_trigger on
        enable_view on
     fts3_tokenizer off
 legacy_alter_table off
 legacy_file_format off
     load_extension on
   no_ckpt_on_close off
     reset_database off
  reverse_scanorder off
    stmt_scanstatus off
        trigger_eqp off
     trusted_schema off
    writable_schema off
sqlite>
```

Setting up box mode:
```
.mode box
```

Taking a look at the available tables:
```
.tables
```

Output:
```
sqlite> .tables
customers     orders        orders_items  products
sqlite>
```

Taking a look at the schemas:

```
.schema
```

Output:
```
sqlite> .schema
CREATE TABLE products (sku text,desc text,wholesale_cost decimal(10,2),dims_cm array);
CREATE TABLE customers (customerid integer,name text,address text,citystatezip text,birthdate text,phone text,timezone text,lat decimal(10,5),long decimal(10,5));
CREATE TABLE orders (orderid text,customerid text,ordered timestamp,shipped timestamp,total decimal(10,2),items array);
CREATE TABLE orders_items (orderid integer,sku text,qty integer,unit_price decimal(10,2));
sqlite>
```

Previewing tables:

```sql
SELECT * FROM customers LIMIT 5;
```

