# ER Diagram Workshop – Submission Template

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
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

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
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

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

<img width="838" height="862" alt="Screenshot 2026-04-30 161334" src="https://github.com/user-attachments/assets/148f5b5f-9e45-45d9-91d2-24fc292d5699" />

### Entities and Attributes

| Entity      | Attributes (PK, FK)                                                                                | Notes                                         |
| ----------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------|
| CUSTOMER    | customer_id (PK), name, phone, email                                                               | Stores customer details                      |
| RESERVATION | reservation_id (PK), date, time, number_of_guests, customer_id (FK), waiter_id (FK), table_id (FK) | Stores reservation information               |
| TABLE       | table_id (PK), capacity, status                                                                    | Stores restaurant table details              |
| WAITER      | waiter_id (PK), name, contact                                                                      | Stores waiter information                    |
| ORDER       | order_id (PK), order_time, reservation_id (FK)                                                     | Stores order details for reservations        |
| ORDER_ITEM  | order_id (PK, FK), dish_id (PK, FK), quantity                                                      | Represents dishes included in an order       |
| DISH        | dish_id (PK), dish_name, price, category_id (FK)                                                   | Stores menu item details                     |
| CATEGORY    | category_id (PK), category_name                                                                    | Stores dish categories                       |
| BILL        | bill_id (PK), total_amount, service_charge, reservation_id (FK)                                    | Stores billing details                       |

### Relationships and Constraints

| Relationship                   | Cardinality | Participation                      | Notes                                                                       |
| ------------------------------ | ----------- | ---------------------------------- | --------------------------------------------------------------------------- |
|RESERVATION assigned to TABLE   | M : 1       | Total participation of RESERVATION | Many reservations can be assigned to one table at different times           |
| RESERVATION assigned to WAITER | M : 1       | Partial participation of WAITER    | A waiter can handle many reservations                                       |
| RESERVATION has ORDER          | 1 : M       | Total participation of ORDER       | One reservation can have multiple orders                                    |
| ORDER contains ORDER_ITEM      | 1 : M       | Total participation of ORDER_ITEM  | One order contains many order items                                         |
| DISH included in ORDER_ITEM    | 1 : M       | Total participation of ORDER_ITEM  | One dish can appear in many order items                                     |
| DISH belongs to CATEGORY       | M : 1       | Total participation of DISH        | Many dishes belong to one category                                          |
| RESERVATION generates BILL     | 1 : 1       | Total participation of BILL        | Each reservation generates exactly one bill   

### Assumptions
- A customer can make multiple reservations, but each reservation is made by only one customer.
- A reservation is assigned to one table and one waiter at a time.
- An order may contain multiple dishes through ORDER_ITEM.
- Each dish belongs to only one category.
- Every reservation generates exactly one bill.
-Table availability is managed using the status attribute.
- ORDER_ITEM is a weak/associative entity used to resolve the many-to-many relationship between ORDER and DISH

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
