# Retrieve Data from Database (SELECT query)

## Basic SELECT

```sql
SELECT * FROM student;
```

This will select all columns from the `student` table.

### SELECT with Conditions

```sql
-- Select students with first name 'John'
SELECT * FROM student WHERE first_name = 'John';

-- Select students born after January 1, 2000
SELECT * FROM student WHERE date_of_birth > '2000-01-01';

-- Select students with email ending in '.com'
SELECT * FROM student WHERE email LIKE '%.com';

-- Select students with phone numbers starting with '123'
SELECT * FROM student WHERE phone_number LIKE '123%';
```

### SELECT with Logical Operators

```sql
-- Select students with first name 'John' AND last name 'Doe'
SELECT * FROM student WHERE first_name = 'John' AND last_name = 'Doe';

-- Select students with first name 'John' OR last name 'Doe'
SELECT * FROM student WHERE first_name = 'John' OR last_name = 'Doe';

-- Select students not born after January 1, 2000
SELECT * FROM student WHERE NOT (date_of_birth > '2000-01-01');
```

### SELECT with BETWEEN

```sql
-- Select students born between January 1, 2000 and December 31, 2005
SELECT * FROM student WHERE date_of_birth BETWEEN '2000-01-01' AND '2005-12-31';
```

### SELECT with MAX and MIN

```sql
-- Select the oldest student
SELECT * FROM student WHERE date_of_birth = (SELECT MIN(date_of_birth) FROM student);

-- Select the youngest student
SELECT * FROM student WHERE date_of_birth = (SELECT MAX(date_of_birth) FROM student);
```

### SELECT with LIMIT

```sql
-- Select the first 10 students
SELECT * FROM student LIMIT 10;

-- Select the next 10 students (pagination)
SELECT * FROM student LIMIT 10 OFFSET 10;
```

### SELECT with COUNT, AVG, and SUM

```sql
-- Count the number of students
SELECT COUNT(*) FROM student;

-- Calculate the average age of students
SELECT AVG(YEAR(CURRENT_DATE) - YEAR(date_of_birth)) AS average_age FROM student;

-- Calculate the total number of characters in all addresses
SELECT SUM(LENGTH(address)) AS total_address_length FROM student;
```

### SELECT with IN

```sql
-- Select students with specific IDs
SELECT * FROM student WHERE student_id IN (1, 3, 5);
```
