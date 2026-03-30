Student Management System

Overview
This project is a Student Management System made using Python and MySQL. It is used to store and manage student data. The system can add, update, delete, search, and display student records.

Features
- Add student details  
- View all students  
- Update student information  
- Delete student records  
- Search student by ID or name  

Technologies Used
- Python  
- MySQL  
- mysql-connector-python  

Project Structure
student-management-system/
main.py
database.sql
README.md

Database
CREATE DATABASE student_db;

USE student_db;

CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    course VARCHAR(50)
);

Sample Code
import mysql.connector

conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="your_password",
    database="student_db"
)

cursor = conn.cursor()

def add_student(id, name, age, course):
    query = "INSERT INTO students VALUES (%s, %s, %s, %s)"
    values = (id, name, age, course)
    cursor.execute(query, values)
    conn.commit()

def view_students():
    cursor.execute("SELECT * FROM students")
    for row in cursor.fetchall():
        print(row)

How to Run
1. Install Python and MySQL  
2. Install library: pip install mysql-connector-python  
3. Run database.sql in MySQL  
4. Update username and password in code  
5. Run main.py  

What I Learned
- Basic CRUD operations  
- Connecting Python with database  
- Writing SQL queries  

Author
Vaishali Kumari
