## Exercise - 3

3. Write the SQL queries using Data Manipulation Language (DML)
statements

(a) Insert values into employee table with field names using insert
command

```sql
INSERT INTO employee (emp_number, emp_name, emp_dob ,
emp_address , emp_deptno, emp_sal)
values (1004, "mohan", "1985-07-15", "btm layout", 559, 5900);
```

(b) Select the table employee using select command

```sql
SELECT * from employee
```

(c) Update emp dept numbers in employee table using update
command.

```sql
update employee
set emp_address = 'chennai'
where emp_number = 1004;
```

(d) Delete a row from employee table.

```sql
DELETE FROM employee
WHERE emp_number = "1003";
```