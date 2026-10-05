# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
```
SELECT MIN(salary) AS minimum_salary
FROM staff;

```

**Output:**

<img width="465" height="132" alt="image" src="https://github.com/user-attachments/assets/3bffcaa6-aed6-4a62-aef8-0e180a33fe10" />

**Question 2**
```
SELECT MAX(salary) AS maximum_salary
FROM staff;

```

**Output:**

<img width="875" height="425" alt="image" src="https://github.com/user-attachments/assets/9bdd31ed-ebc5-4db3-8870-989522d175e6" />

**Question 3**
```
SELECT SUM(salary) AS total_salary
FROM staff;

```

**Output:**

<img width="898" height="355" alt="image" src="https://github.com/user-attachments/assets/f24af296-df8f-4189-9c33-c8e93a73f9f1" />

**Question 4**
```
SELECT AVG(salary) AS average_salary
FROM staff;
```

**Output:**

<img width="762" height="412" alt="image" src="https://github.com/user-attachments/assets/ddfc41f4-ac85-4013-9917-070f1772cc1c" />

**Question 5**
```
SELECT COUNT(*) AS total_staff
FROM staff;

```

**Output:**

<img width="852" height="402" alt="image" src="https://github.com/user-attachments/assets/920863d4-557f-4d3c-8baa-3af1e19a651d" />

**Question 6**
```
SELECT department, COUNT(*) AS staff_count
FROM staff
GROUP BY department;

```

**Output:**

<img width="842" height="391" alt="image" src="https://github.com/user-attachments/assets/af3c976e-210f-4098-9533-90e73fd643a8" />

**Question 7**
```
SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department;

```

**Output:**

SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department;

**Question 8**
```
SELECT department, AVG(salary) AS average_salary
FROM staff
GROUP BY department;

```

**Output:**

<img width="901" height="355" alt="image" src="https://github.com/user-attachments/assets/cd1bac8a-84ff-4834-a4cf-36916c5f3eef" />

**Question 9**
```
SELECT department, COUNT(*) AS staff_count
FROM staff
GROUP BY department
HAVING COUNT(*) > 2;
```

**Output:**

<img width="842" height="367" alt="image" src="https://github.com/user-attachments/assets/24adec09-4e22-4a37-bb8e-28257870705e" />

**Question 10**
```
SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department
HAVING SUM(salary) > 150000;

```

**Output:**

<img width="906" height="347" alt="image" src="https://github.com/user-attachments/assets/1805bd4e-a87c-46fe-bf10-516c658fff11" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
