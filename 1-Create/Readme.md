# Create Database

Create a database using this query.

```sql
CREATE DATABASE GroceryStore
```

## Create Table

```sql
CREATE TABLE "customers" (
"id" INTEGER NOT NULL UNIQUE,
"name" TEXT NOT NULL,
"points" INTEGER NOT NULL,
"birth_date" TEXT NOT NULL,
"state" TEXT NOT NULL,
PRIMARY KEY("id")
);
```
