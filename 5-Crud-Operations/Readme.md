# CRUD Operations

## Create Table

```sql
USE db_name;

CREATE TABLE Employee (
    Emp_no INT AUTO_INCREMENT PRIMARY KEY,
    E_name VARCHAR(255),
    E_address VARCHAR(255),
    E_ph_no VARCHAR(15),
    Dept_no INT,
    Dept_name VARCHAR(255),
    Job_id INT,
    Salary DECIMAL(10, 2)
);
```

## Alter Table

**Add new column `HIREDATE`  to the `Employee` table.**

```sql
USE db_name;

ALTER TABLE table_name
ADD COLUMN HIREDATE DATE;
```

## Alter column data type

```sql
USE db_name;

ALTER TABLE Employee
MODIFY COLUMN Job_id VARCHAR(255);
```

## Alter Column name

```sql
USE db_name;

ALTER TABLE Employee
CHANGE COLUMN Emp_no E_no INT;
```

## Modify the width of the column/field

Change size of the column/field

```sql
USE db_name;

ALTER TABLE Employee
MODIFY COLUMN Job_id VARCHAR(50);
```
