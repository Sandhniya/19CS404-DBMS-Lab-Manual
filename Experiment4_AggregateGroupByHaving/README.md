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
--
What is the average dosage prescribed for each medication?

```sql
Medication     AvgDosage
-------------  ----------
Ciprofloxacin  500.0
Doxorubicin    60.0
Ibuprofen      400.0
Levothyroxine  50.0
Lisinopril     10.0
MMR            0.5
Pending        0.0
Prenatal vita  1.0
Sertraline     50.0
Topiramate     25.0

SELECT
  Medication,
  AVG(Dosage) AS AvgDosage
FROM
  Prescriptions
GROUP BY
  Medication;


```

**Output:**

<img width="651" height="764" alt="image" src="https://github.com/user-attachments/assets/b011e3f6-be31-4914-b3d4-4941aa6d7892" />


**Question 2**
---
How many patients are there in each city?
```sql
Address     TotalPatients
----------  -------------
Berlin      3
Chicago     4
Mexico      3

select Address,count(*)
as TotalPatients
from Patients
group by Address

```

**Output:**

<img width="622" height="401" alt="image" src="https://github.com/user-attachments/assets/50ab7e65-1837-4933-985e-71de65cfc89d" />


**Question 3**
---

Write a SQL Query to find how many medications are prescribed for each patient?
```sql

PatientID   AvgMedications
----------  --------------
4           5
6           1
7           1
8           3

SELECT PatientID,COUNT(*) AS 
AvgMedications
FROM MedicalRecords
GROUP BY PatientID;

```

**Output:**

<img width="699" height="619" alt="image" src="https://github.com/user-attachments/assets/8d6b751d-db08-4bc4-88c7-08fef0924d53" />


**Question 4**
---
Write a SQL query to find the maximum purchase amount.

```sql
ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001

SELECT
  MAX(purch_amt) AS MAXIMUM
FROM
  orders;

```

**Output:**

<img width="424" height="297" alt="image" src="https://github.com/user-attachments/assets/f1350915-fb55-4688-b1fc-6f5ce0550bfd" />


**Question 5**
---
Write a SQL query to find the total income of employees aged 40 or above.

```sql
name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

SELECT
  SUM(income) AS total_income
FROM
  employee
WHERE
  age >= 40;

```

**Output:**

<img width="428" height="306" alt="image" src="https://github.com/user-attachments/assets/e3d61a63-f4f7-455d-8e8b-80009f253c97" />


**Question 6**
---
Write a SQL query to find the number of employees whose age is greater than 32.

```sql
SELECT
  COUNT(*) AS COUNT
FROM
  employee
WHERE
  age > 32;

```

**Output:**

<img width="408" height="308" alt="image" src="https://github.com/user-attachments/assets/fe8729a6-2f05-4b9f-bd21-daf56b607234" />


**Question 7**
---
Write a SQL query to find the average length of names for people living in Chennai?

```sql
name        type
----------  ----------
id          INTEGER
name        TEXT   
city        TEXT
email       TEXT
phone       INTEGER

SELECT
  AVG(LENGTH(name)) AS avg_name_length
FROM
  customer
WHERE
  city = 'Chennai';

```

**Output:**

<img width="664" height="460" alt="image" src="https://github.com/user-attachments/assets/6d830aea-ad24-4cfa-8e1c-22f097fc1c47" />


**Question 8**
---
Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the maximum work hours for each date, and excludes dates where the maximum work hour is not greater than 12.

```sql
jdate       MAX(workhour)
----------  -------------
2004.0      15
2006.0      15

SELECT
  jdate,
  MAX(workhour) AS "MAX(workhour)"
FROM
  employee1
GROUP BY
  jdate
HAVING
  MAX(workhour) > 12;

```

**Output:**

<img width="644" height="353" alt="image" src="https://github.com/user-attachments/assets/5d5271c7-3246-4d8f-9e6d-5d155395e25a" />


**Question 9**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the total work hours for each occupation, and excludes occupations where the total work hour sum is not greater than 20.

```sql
occupation  SUM(workhour)
----------  -------------
Business    30
Doctor      30
Engineer    24
Teacher     27
SELECT
  occupation,
  SUM(workhour) AS "SUM(workhour)"
FROM
  employee1
GROUP BY
  occupation
HAVING
  SUM(workhour) > 20;

```

**Output:**

![Output9](output.png)

**Question 10**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the average work hours for each occupation, and includes only those occupations where the average work hour falls between 10 and 12.

```sql
Result
occupation  AVG(workhour)
----------  -------------
Business    10.0
Engineer    12.0

SELECT
  occupation,
  AVG(workhour) AS "AVG(workhour)"
FROM
  employee1
GROUP BY
  occupation
HAVING
  AVG(workhour) BETWEEN 10 AND 12;



```

**Output:**

<img width="669" height="377" alt="image" src="https://github.com/user-attachments/assets/268a29f5-1348-40e5-b79c-5f4062f727ab" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
