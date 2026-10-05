# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
From the following tables write a SQL query to find those customers with a grade less than 300. Return cust_name, customer city, grade, Salesman, salesmancity. The result should be ordered by ascending customer_id

```
select c.cust_name,
       c.city,
       c.grade,
       s.name as Salesman,
       s.city
from customer c
INNER JOIN salesman s
on c.salesman_id = s.salesman_id
where c.grade < 300
order by c.customer_id;
```

**Output:**

<img width="1312" height="699" alt="image" src="https://github.com/user-attachments/assets/c376deb7-befc-4003-a87f-e410dad7f4b9" />

**Question 2**
Write the SQL query that achieves the selection of all columns from the "customer" table (aliased as "c"), with a left join on the "salesman_id" column and a condition filtering for salesmen with the name 'Mc Lyon'.



```
SELECT c.*
FROM customer AS c
LEFT JOIN salesman AS s
  ON c.salesman_id = s.salesman_id
WHERE s.name = 'Mc Lyon';
```

**Output:**

<img width="1298" height="363" alt="image" src="https://github.com/user-attachments/assets/768af961-c34a-4ea8-ac85-3332f5e94e28" />

**Question 3**
Write a SQL statement to make a report with customer name, city, order number, order date, and order amount in ascending order according to the order date to determine whether any of the existing customers have placed an order or not.



```
SELECT 
    c.cust_name,
    c.city AS "city",
    o.ord_no AS "ord_no",
    o.ord_date AS "ord_date",
    o.purch_amt AS "Order Amount"
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
ORDER BY 
    o.ord_date;
```

**Output:**

<img width="1199" height="779" alt="image" src="https://github.com/user-attachments/assets/ea36b63f-a331-4585-b97b-1f84c7a5ff75" />

**Question 4**
From the following tables write a SQL query to locate those salespeople who do not live in the same city where their customers live and have received a commission of more than 12% from the company. Return Customer Name, customer city, Salesman, salesman city, commission.



```
SELECT 
    c.cust_name AS "Customer Name ",
    c.city ,
    s.name AS "Salesman",
    s.city ,
    s.commission AS "commission"
FROM 
    customer c
INNER JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    c.city <> s.city
    AND s.commission > 0.12;

```

**Output:**

<img width="1285" height="522" alt="image" src="https://github.com/user-attachments/assets/42e88dae-412a-4f0c-a2c3-d0691d5a2a5d" />

**Question 5**
Write the SQL query that achieves the selection of the first name from the "patients" table (aliased as "patient_name") and all columns from the "test_results" table (aliased as "t"), with an inner join on the "patient_id" column.



```
SELECT 
    p.first_name AS patient_name,
    t.*
FROM 
    patients p
INNER JOIN 
    test_results t ON p.patient_id = t.patient_id;
```

**Output:**

<img width="1206" height="350" alt="image" src="https://github.com/user-attachments/assets/d6a156b1-4bf4-4b96-9f6d-0a0fb50bd994" />

**Question 6**
Write the SQL query that achieves the selection of the "cust_name" column from the "customer" table (aliased as "c"), and the "ord_no," "ord_date," and "purch_amt" columns from the "orders" table (aliased as "o"), with a left join on the "customer_id" column and a condition filtering for orders with a purchase amount greater than 1000.



```
SELECT 
    c.cust_name ,
    o.ord_no ,
    o.ord_date ,
    o.purch_amt 
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
WHERE 
    o.purch_amt > 1000;

```

**Output:**

<img width="1214" height="563" alt="image" src="https://github.com/user-attachments/assets/ccee6b2a-53ff-4952-85f9-0c6bc96d83c6" />

**Question 7**
From the following tables write a SQL query to find the details of an order. Return ord_no, ord_date, purch_amt, Customer Name, grade, Salesman, commission.



```
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM 
    orders o
INNER JOIN 
    customer c ON o.customer_id = c.customer_id
INNER JOIN 
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1300" height="751" alt="image" src="https://github.com/user-attachments/assets/82e5dbe4-b3fc-4adb-9f40-879f7ff2bab6" />

**Question 8**
Write the SQL query that achieves the selection of the date of birth from the "patients" table (aliased as "p") and all columns from the "appointments" table (aliased as "a"), with an inner join on the "patient_id" column and a condition filtering for patients with the first name 'Alice'.



```
SELECT 
    p.date_of_birth AS "date_of_birth",
    a.*
FROM 
    patients p
INNER JOIN 
    appointments a ON p.patient_id = a.patient_id
WHERE 
    p.first_name = 'Alice';
```

**Output:**

<img width="1129" height="237" alt="image" src="https://github.com/user-attachments/assets/b45a814f-5ee1-4867-aaa5-4386cccfd120" />

**Question 9**
From the following tables write a SQL query to find salespeople who received commissions of more than 12 percent from the company. Return Customer Name, customer city, Salesman, commission.



```
SELECT 
    c.cust_name AS "Customer Name",
    c.city ,
    s.name AS "Salesman",
    s.commission
FROM 
    customer c
INNER JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    s.commission > 0.12;
```

**Output:**

<img width="1178" height="633" alt="image" src="https://github.com/user-attachments/assets/20aeeb18-a052-4d5b-a866-dd26ff1515ee" />

**Question 10**
Write the SQL query that achieves the selection of admission dates from the "patients" table and surgery dates from the "surgeries" table, with an inner join on the "patient_id" column.



```
SELECT 
    p.admission_date ,
    s.surgery_date 
FROM 
    patients p
INNER JOIN 
    surgeries s ON p.patient_id = s.patient_id;

```

**Output:**

<img width="814" height="450" alt="image" src="https://github.com/user-attachments/assets/90caa636-f3ac-41df-9b01-1ec8bc9db008" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
