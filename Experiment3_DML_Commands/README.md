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
--
-- Write a SQL statement to Update the reorder level to 20 where the quantity in stock is less than 10 and product category is 'Snacks' in the products table.

```sql          
-- update Products
set reorder_lvl=20
where quantity<10 and category ='Snacks';
```

**Output:**


<img width="825" height="372" alt="image" src="https://github.com/user-attachments/assets/e0080844-fd32-402c-a672-4aa81ea37b5e" />


**Question 2**
---
-- Write a SQL statement to Increase the selling price by 15% in the products table where quantity in stock is less than 50 and supplier ID is 10.

```sql          
-- update Products 
set sell_price=sell_price*1.15
where quantity <50 and supplier_id =10;
```

**Output:**


<img width="837" height="340" alt="image" src="https://github.com/user-attachments/assets/3467ada1-cce6-45b2-99b0-c1f1b61be889" />

**Question 3**
---
-- Write a SQL statement to change the EMAIL and COMMISSION_PCT column of the following EMPLOYEES table with 'not available' and 0.55 for those employees whose DEPARTMENT_ID is 110.

```sql                
-- UPDATE Employees
set EMAIL='not available',commission_pct=0.55
where DEPARTMENT_ID =110;
```

**Output:**


<img width="847" height="298" alt="image" src="https://github.com/user-attachments/assets/8b229b5b-5dfb-4cfa-9e63-379707e6ac49" />


**Question 4**
---

v-- Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.
```sql              
-- update Employees
set hire_date='2024-01-24';
```

**Output:**

<img width="837" height="193" alt="image" src="https://github.com/user-attachments/assets/3cc55d66-cfc7-4f0c-9e5b-c05e07506ac8" />


**Question 5**
---
-- Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

```sql              
-- update Products
set product_name='Premium Bread'
where product_id=5;
```

**Output:**

<img width="817" height="275" alt="image" src="https://github.com/user-attachments/assets/63f916b0-a72e-46fb-b6bb-393cf4116a47" />


**Question 6**
---
-- Write a SQL query to Delete customers from 'customer' table where 'GRADE' is exactly 2.

```sql                    
-- delete from customer
where grade =2;
```

**Output:**

<img width="720" height="446" alt="image" src="https://github.com/user-attachments/assets/adeb4eb5-a9b0-48fc-9fb4-2e31e9a2e3b2" />


**Question 7**
---
--Write a SQL query to Delete customers with 'GRADE' 3 and whose 'CUST_NAME' contains the substring 'BBB', and 'PAYMENT_AMT' is greater than 2000

```sql                                                                                                                      -- delete from customer
where grade= 3 
and cust_name like '%BBB%' 
and payment_amt>2000;                                                                                                                                                                                                                                                                                                                                                                              
```

**Output:**

<img width="828" height="351" alt="image" src="https://github.com/user-attachments/assets/ae2166d0-4c2d-4e52-9618-5cb54f432766" />


**Question 8**
---
-- Write a SQL query to Delete customers from 'customer' table where 'AGENT_CODE' is either 'A003' or 'A008'.
```sql                                                                                                                                                                                                                                                -- delete from customer
where agent_code IN('A003','A008');                                                                                                                              
```

**Output:**

<img width="724" height="817" alt="image" src="https://github.com/user-attachments/assets/6d08c7f8-67f6-4439-89b3-d37327ebe9ff" />


**Question 9**
---
-- Write a SQL query to Delete customers from 'customer' table where 'CUST_CITY' is not 'New York' and 'OUTSTANDING_AMT' is greater than 5000.- Paste Question 9 here

```-- DELETE FROM CUSTOMER
WHERE CUST_CITY != 'New York'
and outstanding_AMT >5000;sql                                                                                                                                                                                                                                                                                                                                    
```

**Output:**

<img width="836" height="404" alt="image" src="https://github.com/user-attachments/assets/f719ac22-2389-4410-8aa1-2171eb853746" />


**Question 10**
-- Write a SQL query to delete a doctor from Doctors table whose Specialization is 'Pediatrics' and First name is 'Michael'.

```sql                                                                                                                                                                                                                                                                                                                                                      
-- delete from Doctors
where specialization like '%Pediatric%'
and first_name ='Michael';
```

**Output:**
<img width="802" height="265" alt="image" src="https://github.com/user-attachments/assets/d12dc0f9-8987-4346-abff-81213aa3a59e" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
