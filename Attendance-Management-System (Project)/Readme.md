# Attendance Management System

## MYSQL Queries

**Create Database:**

```sql
CREATE DATABASE Attendance_Management_System;
```

**Create Students table:**

```sql
USE attendance_management_system;

CREATE TABLE students (
    student_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    roll_no VARCHAR(20) NOT NULL UNIQUE,
    major VARCHAR(100)
);

```

**Create Courses Table:**

```sql
USE attendance_management_system;  

CREATE TABLE courses (
    course_id INT AUTO_INCREMENT PRIMARY KEY,
    course_name VARCHAR(100) NOT NULL,
    course_code VARCHAR(10) UNIQUE NOT NULL,
    credit_hours INT NOT NULL
);
```

**Create Attendance Records Table:**

```sql
USE attendance_management_system;  

CREATE TABLE attendance_records (
    attendance_id INT AUTO_INCREMENT PRIMARY KEY,
    student_id INT,
    course_id INT,
    attendance_date DATE NOT NULL,
    status ENUM('Present', 'Absent', 'Leave') NOT NULL,
    remarks TEXT,
    FOREIGN KEY (student_id) REFERENCES students(student_id) ON DELETE CASCADE,
    FOREIGN KEY (course_id) REFERENCES courses(course_id) ON DELETE CASCADE
);
```

**Insert Students:**

```sql
USE attendance_management_system;  

INSERT INTO students (name, email, roll_no, major) VALUES
('Sarmad', 'sarmad@example.com', 'B-27007', 'Software Engineering'),
('Kashif', 'kashif@example.com', 'B-27095', 'Computer Science'),
('Subhan', 'subhan@example.com', 'B-27001', 'Computer Science'),
('Kamran', 'kamran@example.com', 'B-27002', 'Computer Science'),
('Ahmed', 'ahmed@example.com', 'B-27003', 'Computer Science'),
('Imran', 'imran@example.com', 'B-27004', 'Computer Science'),
('Tariq', 'tariq@example.com', 'B-27005', 'Computer Science'),
('Usman', 'usman@example.com', 'B-27006', 'Computer Science'),
('Waqas', 'waqas@example.com', 'B-27008', 'Information Technology'),
('Yousaf', 'yousaf@example.com', 'B-27009', 'Information Technology');

```

**Insert Courses:**

```sql
USE attendance_management_system;  

INSERT INTO courses (course_name, course_code, credit_hours) VALUES
('Web Development', 'CS101', 3),
('Database Management', 'IT201', 3),
('Software Engineering Principles', 'SE101', 3),
('Data Structures and Algorithms', 'CS201', 4),
('Computer Networks', 'CS301', 3),
('Artificial Intelligence', 'CS401', 3),
('Cloud Computing', 'IT301', 3),
('Mobile Application Development', 'SE201', 3),
('Machine Learning', 'CS402', 3),
('Natural Language Processing', 'CS403', 3),
('Computer Graphics', 'CS501', 3),
('Operating Systems', 'CS302', 3);

```

**Insert attendance:**

```sql
USE attendance_management_system;  

INSERT INTO attendance_records (student_id, course_id, attendance_date, status) VALUES
(1, 1, '2024-05-01', 'Present'),
(2, 1, '2024-05-01', 'Absent'),
(3, 2, '2024-05-01', 'Present'),
(4, 2, '2024-05-01', 'Leave'),
(5, 3, '2024-05-01', 'Present'),
(6, 3, '2024-05-01', 'Absent'),
(7, 1, '2024-05-02', 'Present'),
(8, 2, '2024-05-02', 'Present'),
(9, 3, '2024-05-02', 'Absent'),
```

**Applying Join:**

```sql
USE attendance_management_system;  

SELECT s.name AS student_name, a.attendance_date, a.status
FROM students s
JOIN attendance_records a ON s.student_id = a.student_id;

```

This query will return all the students along with their attendance records for each day. The `JOIN` keyword is used to combine two tables.
