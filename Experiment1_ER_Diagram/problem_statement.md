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
<img width="1100" height="662" alt="image" src="https://github.com/user-attachments/assets/c79f68e5-f4bf-45b4-a127-f5a3fa03e1d8" />


### Entities and Attributes

<img width="1022" height="356" alt="image" src="https://github.com/user-attachments/assets/2105805b-465b-4fbb-b1f1-978ec423e6ed" />


### Relationships and Constraints
<img width="1107" height="377" alt="image" src="https://github.com/user-attachments/assets/4f7619da-14e4-49b9-baf7-b6cc958809dc" />


### Assumptions
1. Each session involves exactly one trainer and one member.
2. Programs are predefined (Yoga, Zumba, Weight Training, etc.).
3. Payments are only for membership or session bookings.


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
<img width="1056" height="702" alt="image" src="https://github.com/user-attachments/assets/d22e5083-efbb-4726-b09d-c732c7e52ce2" />


### Entities and Attributes

<img width="928" height="305" alt="image" src="https://github.com/user-attachments/assets/e543cdf8-458b-42a9-8c10-04c67d791fca" />


### Relationships and Constraints

<img width="762" height="175" alt="image" src="https://github.com/user-attachments/assets/eabad69d-d813-4ec6-801f-0744bc3d3586" />


### Assumptions
1. Books can be borrowed multiple times by different Members.
2. Each Event happens in one Room at a specific time.
3. , A Speaker can participate in multiple Events.

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
<img width="1102" height="545" alt="image" src="https://github.com/user-attachments/assets/70935812-66c4-4977-b3b7-538df293fea6" />


### Entities and Attributes

<img width="927" height="266" alt="image" src="https://github.com/user-attachments/assets/9cdfedd1-cf55-4b80-8dc9-6981f33e938e" />


### Relationships and Constraints

<img width="802" height="205" alt="image" src="https://github.com/user-attachments/assets/190bcc59-9ce8-4f85-8456-cb7988dbba0f" />

### Assumptions
1. One reservation uses one table and one waiter.
2. Bill is generated automatically after service.
3. Customer details stored for every reservation.

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
