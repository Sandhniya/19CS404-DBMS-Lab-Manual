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
--
--Write a SQL query that retrieve all the columns from the table "Grades", where the grade is equal to the maximum grade achieved in each subject

```SELECT * FROM GRADES t1
where grade in (select max(grade) from GRADES t2 where t1.subject=t2.subject);-- Paste your SQL code below for Question 1
```

**Output:**

<img width="825" height="222" alt="image" src="https://github.com/user-attachments/assets/d3c29182-1349-4802-aa6a-5df03b4e0529" />


**Question 2**
---
-- From the following tables write a SQL query to find the order values greater than the average order value of 10th October 2012. Return ord_no, purch_amt, ord_date, customer_id, salesman_id.

```
SELECT * from ORDERS
where purch_amt >(select avg(purch_amt) from ORDERS where ord_date='2012-10-10');sql                                                                                                                                                                              
```

**Output:**

<img width="780" height="245" alt="image" src="https://github.com/user-attachments/assets/9a0e6ce5-a43d-4d18-9e55-63739aeb3228" />


**Question 3**
---
-- Write a SQL query to List departments with names longer than the average length


```sql                                                                                                                                                                                                                                                                    
                                                                                                               SELECT department_id,department_name from Departments
where length(department_name)>(select avg(length(department_name)) from Departments);                                                                                                                                                             
```

**Output:**

<img width="593" height="339" alt="image" src="https://github.com/user-attachments/assets/e727b4cd-5441-4f88-82e4-30742075ee0b" />


**Question 4**
----- Write a SQL query that retrieves the names of students and their corresponding grades, where the grade is equal to the maximum grade achieved in each subject.-- Paste Question 4 here

```SELECT student_name,grade from GRADES t1
WHERE grade=(select max(grade) from GRADES t2 where t1.subject=t2.subject);sql                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
```

**Output:**

<img width="688" height="343" alt="image" src="https://github.com/user-attachments/assets/2536f84c-fbad-4a7e-94a4-1694e6e8f78c" />

**Question 5**
---
-- Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose Address as Delhi and age below 30
                                
```sql                                                                                                                                                                                                                                                                                                                                                                           SELECT * from CUSTOMERS
WHERE ADDRESS='Delhi' and AGE<30
ORDER BY ID;                                                                                                                                                                                                                                                                     

```

**Output:**

<img width="783" height="196" alt="image" src="https://github.com/user-attachments/assets/6277c94f-56c6-466e-a9b1-6ad8b6f3f0d8" />

**Question 6**
---
-- Write a SQL query that retrieves the names of students and their corresponding grades, where the grade is equal to the minimum grade achieved in each subject.

```sql                                                                                                                                                                                                                                                                                                                                                                           SELECT student_name,grade from GRADES t1    
where grade=(select min(grade) from GRADES t2 where t1.subject=t2.subject);                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               

```

**Output:**

<img width="714" height="362" alt="image" src="https://github.com/user-attachments/assets/9157a6b3-7e7f-482b-b783-9835d5672127" />


**Question 7**
---
-Write a SQL query to Identify customers whose city is different from the city of the customer with the highest ID

```sql                                                                                                                                                                                                                                                  SELECT * from customer    
where city<>(select city from customer where id=(select max(id) from customer));                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        
-- Paste your SQL code below for Question 7
```

**Output:**

SELECT * from customer
where city<>(select city from customer where id=(select max(id) from customer));

**Question 8**
---
-- Write a query to display all the customers whose ID is the difference between the salesperson ID of Mc Lyon and 2001.

```sql                                                                                                                                                                                                                                                 SELECT * FROM customer
where customer_id=(Select salesman_id-2001 from salesman where name='Mc Lyon');                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             
-- Paste your SQL code below for Question 8
```

**Output:**

<img width="821" height="157" alt="image" src="https://github.com/user-attachments/assets/4e6a7973-9c9d-4c6b-b27d-64726970c3fc" />

**Question 9**
---

- Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose AGE is LESS than $30
SELECT * from CUSTOMERS    

where age<30;
```sql                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        

```

**Output:**  
<img width="841" height="358" alt="image" src="https://github.com/user-attachments/assets/88b00033-4775-435b-a176-17b2ec186889" />

**Question 10**
---
-- Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose Address as Delhi

```sql                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      SELECT * FROM CUSTOMERS
WHERE ADDRESS='Delhi';    
```

**Output:**


<img width="813" height="171" alt="image" src="https://github.com/user-attachments/assets/e3903e2f-84dc-4258-8c17-a65d3e09d9d3" />

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
