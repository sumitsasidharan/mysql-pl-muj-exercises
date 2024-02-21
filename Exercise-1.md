# 1. Write the SQL queries using Data Definition Language (DDL) statements

**Objective:** To perform this practical need to use the below given DDL commands and create the following tables
**DDL commands:** create, alter and drop
**Tables:** student, student_marksheet, employee, emp_dept and emp_sal

## (i) Student table

Create database mydatabase

### (a) Create student table

```sql
CREATE TABLE student(
  student_number int,
  student_name varchar(30),
  student_address varchar(30),
  student_dob date,
  student_branch varchar(30)
);
```

### (b) CREATE TABLE student_marksheet

```sql
CREATE TABLE student_marksheet(
  student_number int primary key,
  student_sem int,
  total_marks int
);
```

## (ii) Employee table

### (c) Create employee table

```sql
CREATE TABLE employee(
  emp_number int primary key,
  emp_name varchar(30),
  emp_dob date,
  emp_address varchar(30),
  emp_deptno int
);
```

### (d) Create employee dept table

```sql
CREATE TABLE emp_dept(
  emp_number int,
  empdept_name varchar(30),
  emp_deptno int
);
```

### (e) CREATE TABLE emp salary

```sql
CREATE TABLE emp_salary(
	emp_number int,
  doj date,
	emp_sal bigint
);
```

### (f) Modify the table student mark sheet using the alter command

For modify the table syntax
ALTER TABLE table_name ADD column_name datatype

For modify the table syntax
ALTER TABLE table_name DROP COLUMN column_name datatype

### (g) Remove the table emp salary using drop command

```sql
DROP TABLE emp_salary
```
