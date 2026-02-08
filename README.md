# SQL JOINs & Window Functions – Car Rental Analysis Project

## Course
Database Development with PL/SQL (INSY 8311)

## Student Information
Name: Kenny NIYONSHUTI  
Student ID: 29367  
Repository Name: plsql_window_functions_29367_Kenny  

---

## Business Problem

This project is based on a car rental company called SwiftRide operating in Rwanda. The company rents different types of vehicles to customers in multiple cities and records rental transactions in a relational database.

The main challenge is that although data exists about customers, cars, and rentals, management does not have clear analytical reports to understand which cars perform best, which customers rent most frequently, and how rental revenue changes over time.

The expected outcome of this project is to provide meaningful insights that help management improve pricing strategies, fleet planning, and customer targeting.

---

## Success Criteria

The project is designed to achieve the following analytical goals using SQL JOINs and Window Functions:

1. Identify the top cars by rental revenue using ranking window functions such as RANK().
2. Calculate running totals of rental revenue over time using SUM() OVER().
3. Measure month-to-month changes in revenue using navigation functions like LAG().
4. Segment customers into four groups based on rental activity using NTILE(4).
5. Compute moving averages of revenue using AVG() OVER() to observe trends.

---

## Database Schema

The project uses a relational database named `swiftride` with three main tables:

### Table: cars
- car_id (Primary Key)
- brand
- model
- year
- daily_rate

### Table: customers
- customer_id (Primary Key)
- full_name
- email
- city
- signup_date

### Table: rentals
- rental_id (Primary Key)
- customer_id (Foreign Key → customers.customer_id)
- car_id (Foreign Key → cars.car_id)
- rental_date
- return_date
- total_amount

Relationships:
- One customer can have many rentals.
- One car can be rented many times.
- The rentals table connects customers and cars.

An ER diagram is included in the repository to illustrate these relationships.

---

## Part A: SQL JOINs

The following SQL JOIN types were implemented using the SwiftRide database:

1. INNER JOIN  
Used to retrieve valid rental records that have matching customers and cars.

2. LEFT JOIN  
Used to identify customers who have never made a rental.

3. RIGHT JOIN / FULL OUTER JOIN  
Used to detect cars that have never been rented.

4. FULL OUTER JOIN  
Used to compare customers and cars including unmatched records.

5. SELF JOIN  
Used to compare customers within the same city.

Each JOIN includes:
- The SQL query with comments
- A screenshot of the result
- A short business interpretation

---

## Part B: Window Functions

The project demonstrates four categories of window functions:

### 1. Ranking Functions
- ROW_NUMBER()
- RANK()
- DENSE_RANK()
- PERCENT_RANK()

Use case: Ranking cars or customers by revenue.

### 2. Aggregate Window Functions
- SUM() OVER()
- AVG() OVER()

Use case: Running totals and moving averages of rental revenue.

### 3. Navigation Functions
- LAG()
- LEAD()

Use case: Comparing revenue from one month to the previous month.

### 4. Distribution Functions
- NTILE(4)
- CUME_DIST()

Use case: Segmenting customers into quartiles based on rental activity.

Each window function includes:
- The SQL query with comments
- A screenshot of the result
- A business interpretation

---

## Results Analysis

### Descriptive Analysis – What Happened?
The analysis shows which cars generate the most rental revenue and which customers rent most frequently. It also shows how rental revenue changes over time.

### Diagnostic Analysis – Why Did It Happen?
High-revenue cars are rented more often because of better pricing and availability. Customers in major cities such as Kigali tend to rent more frequently than those in smaller cities.

### Prescriptive Analysis – What Should Be Done Next?
The company should invest more in high-performing car models and create loyalty programs for frequent customers. It should also consider adjusting pricing and promotions in lower-performing cities.

---

## References

W3Schools SQL JOIN Tutorial  

---

## Integrity Statement

All sources were properly cited.  
Implementations and analysis represent original work.  
No AI-generated content was copied without attribution or adaptation.

---

## Evidence of Work

Screenshots included in this repository show executed queries and real results generated from the SwiftRide database.
