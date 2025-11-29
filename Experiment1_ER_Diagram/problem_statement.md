# ER Diagram Workshop – Submission Template
name : sandhiya sree b
## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
<img width="818" height="904" alt="image" src="https://github.com/user-attachments/assets/331231a7-9d73-4110-b791-b2dbd276e04f" />


### Entities and Attributes

| Entity	|Attributes (PK, FK)	|Notes
|Member	|MemberID ,Membership	 |Store member details
|Trainer	|TrainerID,Name,Email,PhoneNumber	|Store Trainer details
|Program	|ProgramID,Cost	|Programs like Zumbz/yoga
|Session	|SessionID,SessionDate	|Tracks attendance
|Payment	|PaymentID,Amount	|Tracks payments by members|


### Relationships and Constraints
<img width="828" height="304" alt="image" src="https://github.com/user-attachments/assets/bfed91b2-7264-4de7-b158-899ee7e54b9f" />




### Assumptions
Program = recurring class; Session = specific instance.
Payments cover both memberships and sessions.
A Session links one Member and one Trainer.


---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
<img width="639" height="748" alt="image" src="https://github.com/user-attachments/assets/43d69e05-92e5-45f6-a9e8-d1fd4b2d2c10" />


### Entities and Attributes

<img width="838" height="326" alt="image" src="https://github.com/user-attachments/assets/9802bd63-ace9-4c99-bf25-89a1d4384f50" />


### Relationships and Constraints

<img width="826" height="312" alt="image" src="https://github.com/user-attachments/assets/d914943e-0b58-445b-a673-fc2548d02e61" />


### Assumptions
Overdue fines are stored per Loan record.
BookCopy not modeled
Rooms serve both events and study bookings.

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
<img width="573" height="688" alt="image" src="https://github.com/user-attachments/assets/cdf4cda1-6901-413b-ab54-1473842cd5cc" />


### Entities and Attributes
<img width="832" height="432" alt="image" src="https://github.com/user-attachments/assets/6f3feb39-72de-4c17-a00b-c6165177182e" />


### Relationships and Constraints

<img width="825" height="313" alt="image" src="https://github.com/user-attachments/assets/25dabf22-acdd-4f3f-9e8f-45de04788b64" />


### Assumptions
Walk-in customers are still recorded
One bill per reservation
Split payments not modeled; could extend with a Payment entity.

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
