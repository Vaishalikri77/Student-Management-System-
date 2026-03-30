# Student-Management-System-
Built a Student Management System using Python and SQL to manage student records with features like add, update, delete, and search.

🔹 Features
Add new student records
Update existing student details
Delete student records
Search student by ID or name
View all student records
Data validation and error handling
🔹 Technologies Used
Python
SQL (MySQL)
MySQL Connector (Python library)

🔹 Project Structure
student-management-system/
 main.py  Main Python file database.sql    SQL file to create database and table README.md       Project documentation
🔹 Database Schema (dataset)
CREATE DATABASE student_db;

USE student_db;

CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    course VARCHAR(50)
);
🔹 Sample Python Code
import mysql.connector

# Connect to database
conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="your_password",
    database="student_db"
)

cursor = conn.cursor()

# Insert data
def add_student(id, name, age, course):
    query = "INSERT INTO students VALUES (%s, %s, %s, %s)"
    values = (id, name, age, course)
    cursor.execute(query, values)
    conn.commit()
    print("Student added successfully")

# View data
def view_students():
    cursor.execute("SELECT * FROM students")
    for row in cursor.fetchall():
        print(row)

# Example usage
add_student(1, "Vaishali", 21, "CSE")
view_students()
🔹 How to Run
Install MySQL and Python

Install required library:

pip install mysql-connector-python
Run the SQL file in MySQL
Update database credentials in main.py

Run the program:

python main.py
🔹 Learning Outcomes
Understanding of CRUD operations
Database integration with Python
Writing SQL queries
Error handling and validation
🔹 Future Improvements
Add GUI (Tkinter / Web Interface)
User authentication system
Export data to Excel
👩‍💻 Author

Vaishali Kumari
