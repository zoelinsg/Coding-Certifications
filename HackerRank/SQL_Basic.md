# SQL (Basic) Certificate - Solution Notes

## Problem 1: Student Analysis

### **Problem Statement**
A school recently conducted its annual examination and wishes to know the list of academically low-performing students to organize extra classes for them. Write a query to return the roll number and names of students who have a total of less than 100 marks including all 3 subjects.

There are two tables in the database:

#### **Schema**
```plaintext
Table: student_information
Columns:
- roll_number (INTEGER) PRIMARY KEY
- name (STRING)

Table: examination_marks
Columns:
- roll_number (INTEGER) PRIMARY KEY
- subject_one (INTEGER)
- subject_two (INTEGER)
- subject_three (INTEGER)
```

### **MySQL 解法**
```sql
SELECT s.roll_number, s.name
FROM student_information s
JOIN examination_marks e ON s.roll_number = e.roll_number
GROUP BY s.roll_number, s.name
HAVING SUM(e.subject_one + e.subject_two + e.subject_three) < 100;
```

### **MSSQL 解法**
```sql
SELECT s.roll_number, s.name
FROM student_information s
JOIN examination_marks e ON s.roll_number = e.roll_number
GROUP BY s.roll_number, s.name
HAVING SUM(e.subject_one + e.subject_two + e.subject_three) < 100;
```

### **PostgreSQL 解法**
```sql
SELECT s.roll_number, s.name
FROM student_information s
JOIN examination_marks e ON s.roll_number = e.roll_number
GROUP BY s.roll_number, s.name
HAVING SUM(e.subject_one + e.subject_two + e.subject_three) < 100;
```

---

## Problem 2: Profitable Stocks

### **Problem Statement**
A stock is considered profitable if the predicted price is strictly greater than the current price. Write a query to find the stock_codes of all the stocks which are profitable based on this definition. Sort the output in ascending order.

There are two tables in the database:

#### **Schema**
```plaintext
Table: price_today
Columns:
- stock_code (STRING) PRIMARY KEY
- price (INTEGER)

Table: price_tomorrow
Columns:
- stock_code (STRING) PRIMARY KEY
- price (INTEGER)
```

### **MySQL 解法**
```sql
SELECT p1.stock_code
FROM price_today p1
JOIN price_tomorrow p2 ON p1.stock_code = p2.stock_code
WHERE p2.price > p1.price
ORDER BY p1.stock_code;
```

### **MSSQL 解法**
```sql
SELECT p1.stock_code
FROM price_today p1
JOIN price_tomorrow p2 ON p1.stock_code = p2.stock_code
WHERE p2.price > p1.price
ORDER BY p1.stock_code;
```

### **PostgreSQL 解法**
```sql
SELECT p1.stock_code
FROM price_today p1
JOIN price_tomorrow p2 ON p1.stock_code = p2.stock_code
WHERE p2.price > p1.price
ORDER BY p1.stock_code;
