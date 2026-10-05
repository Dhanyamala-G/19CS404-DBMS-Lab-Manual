# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
```
CREATE TABLE STUDENT (
    STUDENT_ID NUMBER(5),
    NAME VARCHAR2(30),
    DEPARTMENT VARCHAR2(20),
    MARKS NUMBER(3)
);

DESC STUDENT;
```

**Output:**

<img width="206" height="146" alt="image" src="https://github.com/user-attachments/assets/f5d4ea76-4212-483c-ace6-8f93e36eb8d0" />

**Question 2**
```
ALTER TABLE STUDENT
ADD (ADDRESS VARCHAR2(30));

DESC STUDENT;
```

**Output:**

<img width="242" height="126" alt="image" src="https://github.com/user-attachments/assets/93f1fe60-41cd-47e8-a3b3-c44c27f32807" />

**Question 3**
```
ALTER TABLE STUDENT
MODIFY (NAME VARCHAR2(50));

DESC STUDENT;
```

**Output:**

<img width="202" height="117" alt="image" src="https://github.com/user-attachments/assets/02213424-a55f-4a59-a20f-c2c72c6612d8" />

**Question 4**
```
ALTER TABLE STUDENT
DROP COLUMN ADDRESS;

DESC STUDENT;
```

**Output:**

<img width="217" height="107" alt="image" src="https://github.com/user-attachments/assets/6a8e5aee-be8c-4ae3-92b1-cc5adff9b9a0" />

**Question 5**
```
ALTER TABLE STUDENT
RENAME COLUMN NAME TO STUDENT_NAME;

DESC STUDENT;
```

**Output:**

<img width="208" height="102" alt="image" src="https://github.com/user-attachments/assets/fd95c3af-6281-4d04-9104-c45857687304" />

**Question 6**
```
CREATE TABLE EMPLOYEE (
    EMP_ID NUMBER(5) PRIMARY KEY,
    EMP_NAME VARCHAR2(30) NOT NULL,
    SALARY NUMBER(8,2)
);

DESC EMPLOYEE;
```

**Output:**

<img width="177" height="87" alt="image" src="https://github.com/user-attachments/assets/c8e93806-3cf9-4d68-ad89-5c377e96c9b2" />

**Question 7**
```
CREATE TABLE COURSE (
    COURSE_ID NUMBER(5) PRIMARY KEY,
    COURSE_NAME VARCHAR2(30) UNIQUE,
    DURATION NUMBER(2) CHECK (DURATION > 0)
);

DESC COURSE;
INSERT INTO COURSE VALUES (101, 'Python', 6);
INSERT INTO COURSE VALUES (102, 'Java', 4);

SELECT * FROM COURSE;
```

**Output:**

<img width="992" height="352" alt="image" src="https://github.com/user-attachments/assets/7c0df825-a246-4268-8f24-ae7328a9eac0" />

**Question 8**
```
CREATE TABLE DEPARTMENT (
    DEPT_ID NUMBER(3) PRIMARY KEY,
    DEPT_NAME VARCHAR2(30)
);

CREATE TABLE STUDENT_DEPT (
    STUDENT_ID NUMBER(5) PRIMARY KEY,
    STUDENT_NAME VARCHAR2(30),
    DEPT_ID NUMBER(3),
    FOREIGN KEY (DEPT_ID) REFERENCES DEPARTMENT(DEPT_ID)
);

DESC STUDENT_DEPT;
```

**Output:**

<img width="526" height="192" alt="image" src="https://github.com/user-attachments/assets/7ccf687c-6d53-4455-9368-dc03e8ecf88a" />

**Question 9**
```
CREATE TABLE CUSTOMER (
    CUSTOMER_ID NUMBER(5) PRIMARY KEY,
    CUSTOMER_NAME VARCHAR2(30) NOT NULL,
    CITY VARCHAR2(20) DEFAULT 'Chennai'
);

INSERT INTO CUSTOMER (CUSTOMER_ID, CUSTOMER_NAME)
VALUES (101, 'Ravi');

SELECT * FROM CUSTOMER;
```

**Output:**

<img width="992" height="417" alt="image" src="https://github.com/user-attachments/assets/ae5feed5-a07b-46d0-834f-09ea9ce932ac" />

**Question 10**
```
CREATE TABLE TEMP_STUDENT (
    ID NUMBER(5),
    NAME VARCHAR2(30)
);

RENAME TEMP_STUDENT TO STUDENT_DETAILS;

DESC STUDENT_DETAILS;

DROP TABLE STUDENT_DETAILS;
```

**Output:**

<img width="525" height="165" alt="image" src="https://github.com/user-attachments/assets/c5991895-72ba-4eea-9bfe-42bce5502484" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
