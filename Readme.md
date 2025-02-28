HRIS Employee Management System
Overview
This project is a Human Resource Information System (HRIS) Employee Management System implemented in SQL. It includes tables for managing employees, departments, salaries, and attendance records. Additionally, it features useful queries, stored procedures, views, and triggers.

Features
Employee & Department Management: Store employee details along with department assignments.
Attendance Tracking: Record daily attendance status (Present, Absent, Leave).
Salary Management: Maintain salary history and updates.
SQL Queries:
Retrieve employee details with department information.
Count employees per department.
Get attendance records for a given month.
Stored Procedures & Views:
GetSalaryHistory procedure to track employee salary changes.
ActiveEmployees view for fetching only active employees.
Triggers:
SalaryUpdateTrigger to automatically log salary updates.
Database Schema
Departments (DepartmentID, DepartmentName)
Employees (EmployeeID, FirstName, LastName, Email, JobTitle, DepartmentID, Salary, Status)
Attendance (AttendanceID, EmployeeID, AttendanceDate, Status)
Salaries (SalaryID, EmployeeID, SalaryAmount, EffectiveDate)
Setup Instructions
Create the Database
sql
Copy
Edit
CREATE DATABASE HRIS_Employee_Management;
USE HRIS_Employee_Management;
Run the SQL script (included in HRIS_Employee_Management.sql).
Execute Queries to test functionality.
Example Queries
Retrieve all employees with their department names
sql
Copy
Edit
SELECT E.EmployeeID, E.FirstName, E.LastName, D.DepartmentName, E.JobTitle, E.Salary, E.Status
FROM Employees E
JOIN Departments D ON E.DepartmentID = D.DepartmentID;
Count the number of employees per department
sql
Copy
Edit
SELECT D.DepartmentName, COUNT(E.EmployeeID) AS TotalEmployees
FROM Departments D
LEFT JOIN Employees E ON D.DepartmentID = E.DepartmentID
GROUP BY D.DepartmentName;
Future Enhancements
Employee promotions tracking.
Payroll calculations with deductions and bonuses.
Integration with HRIS SaaS platforms.
Author
[Your Name]

