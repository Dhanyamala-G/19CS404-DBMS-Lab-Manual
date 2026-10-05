# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
```
SELECT *
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

**Output:**

<img width="970" height="322" alt="image" src="https://github.com/user-attachments/assets/d924d03d-9a96-4c62-a084-8c4481563511" />

**Question 2**
```
CREATE TABLE employees (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50),
    department VARCHAR2(50),
    salary NUMBER
);
```

**Output:**

<img width="1032" height="402" alt="image" src="https://github.com/user-attachments/assets/9d1c063d-fedb-48e1-b0be-87502e63defc" />

**Question 3**
```
SELECT *
FROM employees
WHERE department IN (
    SELECT department
    FROM employees
    WHERE salary > 40000
);
```

**Output:**

<img width="1043" height="417" alt="image" src="https://github.com/user-attachments/assets/35891ff7-ca61-4574-8438-35c0121cd4b2" />

**Question 4**
```
SELECT *
FROM employees
WHERE salary > ANY (
    SELECT salary
    FROM employees
    WHERE department = 'HR'
);
```

**Output:**

<img width="942" height="422" alt="image" src="https://github.com/user-attachments/assets/ffe3ce86-3482-4f99-970c-62c86bf0d919" />

**Question 5**
```
SELECT *
FROM employees
WHERE salary > ALL (
    SELECT salary
    FROM employees
    WHERE department = 'HR'
);
```

**Output:**

<img width="1105" height="412" alt="image" src="https://github.com/user-attachments/assets/94b20263-d4c6-4e9a-9b63-779b01a883b2" />

**Question 6**
```
SELECT e.emp_id, e.emp_name, e.department, e.salary
FROM employees e
WHERE e.salary > (
    SELECT AVG(e2.salary)
    FROM employees e2
    WHERE e2.department = e.department
);
```

**Output:**

<img width="1012" height="328" alt="image" src="https://github.com/user-attachments/assets/d1ca5e54-9ba4-4487-be24-8a54341b2a97" />

**Question 7**
```
CREATE VIEW it_employees AS
SELECT emp_id, emp_name, salary
FROM employees
WHERE department = 'IT';

SELECT * FROM it_employees;
```

**Output:**

<img width="965" height="343" alt="image" src="https://github.com/user-attachments/assets/ca2955c1-6915-4819-bd77-f1b7c795d978" />

**Question 8**
```
CREATE VIEW high_salary_employees AS
SELECT emp_id, emp_name, department, salary
FROM employees
WHERE salary > 40000;

SELECT * FROM high_salary_employees;

```

**Output:**

<img width="635" height="177" alt="image" src="https://github.com/user-attachments/assets/1846146f-0ddc-4e0f-b89b-bbf256551b2c" />

**Question 9**
```
CREATE VIEW department_avg_salary AS
SELECT department, AVG(salary) AS average_salary
FROM employees
GROUP BY department;

SELECT * FROM department_avg_salary;

```

**Output:**

<img width="877" height="345" alt="image" src="https://github.com/user-attachments/assets/67d28821-9e03-4efc-9ad7-95e5d8d7da01" />

**Question 10**
```
DROP VIEW high_salary_employees;
```

**Output:**

<img width="937" height="390" alt="image" src="https://github.com/user-attachments/assets/37283bcc-26f5-4a5d-a405-00d59ec3e79f" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
