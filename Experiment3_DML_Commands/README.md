# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
```
CREATE TABLE Student (
    student_id NUMBER,
    student_name VARCHAR2(30),
    department VARCHAR2(20),
    marks NUMBER
);
```

**Output:**

<img width="977" height="358" alt="image" src="https://github.com/user-attachments/assets/53509083-c859-4b2b-843d-525e6c1bb5f3" />

**Question 2**
```
INSERT INTO Student (student_id, student_name, department, marks)
VALUES (101, 'Ravi', 'CSE', 85);

COMMIT;
```

**Output:**

<img width="1078" height="366" alt="image" src="https://github.com/user-attachments/assets/f9d1d488-e701-41f4-954f-7176a8d92268" />

**Question 3**
```
INSERT ALL
    INTO Student VALUES (102, 'Priya', 'ECE', 78)
    INTO Student VALUES (103, 'Arun', 'CSE', 92)
    INTO Student VALUES (104, 'Meena', 'IT', 88)
SELECT * FROM dual;

COMMIT;
```

**Output:**

<img width="257" height="131" alt="image" src="https://github.com/user-attachments/assets/ccb70abf-dba8-46cc-a3fc-331d3a684adc" />

**Question 4**
```
SELECT * FROM Student;
```

**Output:**

<img width="570" height="158" alt="image" src="https://github.com/user-attachments/assets/bd339e8a-f68e-4af1-a0ea-9c039fa97c4c" />

**Question 5**
```
SELECT * FROM Student
WHERE department = 'CSE';
```

**Output:**

<img width="677" height="186" alt="image" src="https://github.com/user-attachments/assets/90c7c07f-6c57-457d-b341-2e7f672fb734" />

**Question 6**
```
UPDATE Student
SET marks = 90
WHERE student_id = 101;

COMMIT;
```

**Output:**

<img width="456" height="490" alt="image" src="https://github.com/user-attachments/assets/e9824250-4f73-4ced-9a12-040be5c4cab4" />

**Question 7**
```
UPDATE Student
SET department = 'CSE'
WHERE student_id = 102;

COMMIT;
```

**Output:**
<img width="445" height="458" alt="image" src="https://github.com/user-attachments/assets/aafee8ea-c37c-4a20-a2dc-63b23d515c6b" />

**Question 8**
```
DELETE FROM Student
WHERE student_id = 104;

COMMIT;
```

**Output:**

<img width="517" height="557" alt="image" src="https://github.com/user-attachments/assets/1295d906-9301-4c3e-a333-42624faab61b" />

**Question 9**
```
SELECT * FROM Student
WHERE marks > 85;
```

**Output:**

<img width="622" height="107" alt="image" src="https://github.com/user-attachments/assets/843e692a-9ac6-4f36-9f74-577aedab6b62" />

**Question 10**
```
CREATE TABLE CSE_Students (
    student_id NUMBER,
    student_name VARCHAR2(30),
    department VARCHAR2(20),
    marks NUMBER
);
INSERT INTO CSE_Students
SELECT * FROM Student
WHERE department = 'CSE';

COMMIT;
SELECT * FROM CSE_Students;
```

**Output:**

<img width="617" height="132" alt="image" src="https://github.com/user-attachments/assets/68ff8de9-38f1-4b9b-98d5-7a2dd1f24925" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
