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
--
<img width="772" height="345" alt="image" src="https://github.com/user-attachments/assets/7d4e5e17-f338-4ec1-9947-6070c46e7188" />


```sql
CREATE TABLE Employees
(
    EmployeeID INTEGER ,
    FirstName TEXT ,
    LastName TEXT,
    HireDate DATE
);

```

**Output:**
<img width="826" height="155" alt="image" src="https://github.com/user-attachments/assets/65a0f50e-cd41-45cd-9445-6049ecb4367a" />


**Question 2**
---
<img width="622" height="169" alt="image" src="https://github.com/user-attachments/assets/11692e41-9f90-41a0-acac-f8a4a296e83a" />


```sql
CREATE TABLE Bonuses
(
    BonusID  INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    BonusAmount REAL CHECK (BonusAmount>0),
    BonusDate DATE,
    Reason TEXT NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)

);
```

**Output:**
<img width="828" height="135" alt="image" src="https://github.com/user-attachments/assets/2cbe228c-ebc3-47e1-b3f3-a8c0d6d5d1db" />


**Question 3**
---
<img width="503" height="260" alt="image" src="https://github.com/user-attachments/assets/4f54c373-b978-41d5-8be6-9076552aa3f4" />


```sql
INSERT INTO Employee(EmployeeID, Name, Department, Salary)
SELECT EmployeeID, Name, Department, Salary FROM  Former_employees;
```

**Output:**
<img width="832" height="189" alt="image" src="https://github.com/user-attachments/assets/3dd565d6-a93d-4e8e-90bf-92002daf69c8" />


**Question 4**
---

<img width="781" height="181" alt="image" src="https://github.com/user-attachments/assets/e734838a-c546-49fd-9522-e6887870f97a" />


```sql

CREATE TABLE Department
(
    DepartmentID INTEGER PRIMARY KEY,
    DepartmentName TEXT UNIQUE NOT NULL,
    Location TEXT
);
```

**Output:**


<img width="832" height="131" alt="image" src="https://github.com/user-attachments/assets/3237db38-3152-45d2-9083-84d9aa18fbb9" />


**Question 5**
---

<img width="828" height="221" alt="image" src="https://github.com/user-attachments/assets/45630d2e-0bdf-4127-b2dd-d584740ca509" />


```sql
CREATE TABLE Employees
(
   EmployeeID INTEGER PRIMARY KEY,
   FirstName  NOT NULL,
   LastName NOT NULL,
   Email UNIQUE,
   Salary CHECK(Salary>0),
   DepartmentID INTEGER,
   FOREIGN KEY(DepartmentID) REFERENCES Departments(DepartmentID)
   
);
```

**Output:**


<img width="815" height="198" alt="image" src="https://github.com/user-attachments/assets/9216891b-7d31-45e7-a57e-65818f9cf5f0" />


**Question 6**
---


<img width="826" height="169" alt="image" src="https://github.com/user-attachments/assets/705ae53d-dcf3-4124-b501-da99a9ae39ea" />


```sql
ALTER TABLE  Student_details ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';

```

**Output:**


<img width="826" height="139" alt="image" src="https://github.com/user-attachments/assets/cecc3d65-d52a-4b50-9f0c-4b09f0783147" />



**Question 7**
---

<img width="722" height="345" alt="image" src="https://github.com/user-attachments/assets/51a80de1-9adf-4cc0-b2be-5c093d3956b8" />


```sql
INSERT INTO Books(ISBN ,Title ,Author) VALUES ('978-6655443321'  , 'Big Data Analytics' ,'Karen Adams');

```

**Output:**


<img width="832" height="178" alt="image" src="https://github.com/user-attachments/assets/26ae4f91-fcab-41f5-8a3a-0febcb80ecef" />


**Question 8**
---

<img width="827" height="269" alt="image" src="https://github.com/user-attachments/assets/471ba0c8-bdee-499d-b5eb-d9bab57103b3" />

```sql
ALTER TABLE Student_details ADD COLUMN  ParentsNumber number;
ALTER TABLE Student_details ADD COLUMN  Adhar_Number number;
```

**Output:**


<img width="834" height="218" alt="image" src="https://github.com/user-attachments/assets/f0a1a4a8-c3eb-482e-9d52-4f2add2ba9b3" />


**Question 9**
---

<img width="815" height="240" alt="image" src="https://github.com/user-attachments/assets/44b0c058-e88b-4f63-96df-6dba8e997e2f" />


```sql
ALTER table Employees ADD COLUMN  Date_of_joining Date ;
ALTER table Employees RENAME Column  job_title to Designation;
```

**Output:**


<img width="832" height="167" alt="image" src="https://github.com/user-attachments/assets/fbcae45f-3c1b-4c80-9ca2-7a0012c8d1e1" />

**Question 10**
---

<img width="693" height="200" alt="image" src="https://github.com/user-attachments/assets/ccce6229-55d6-4cba-8e0b-4d06702e4c1c" />


```sql
Insert into Books( ISBN, Title, Author, Publisher, YearPublished)
select ISBN, Title, Author, Publisher, YearPublished from  Out_of_print_books;
```

**Output:**


<img width="827" height="138" alt="image" src="https://github.com/user-attachments/assets/6493ef47-77cc-406c-a6ff-d2f3ccfdbe1d" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
