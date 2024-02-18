## Exercise - 2

2. Write the SQL queries using Data Manipulation Language (DML)
   statements
   (a) Insert values into student table with field names using insert
   command

```sql
INSERT INTO student (student_number, student_name, student_address, student_dob, student_branch)
VALUES (105, "ramya","chennai", "1987-12-24", "cse");
```

(b) Display the table student using select command

```sql
Select * from student
```

(c) Update student address in student table using update command.

```sql
update student
set student_address = "bangalore"
where student_number = 104;
```

(d) Delete a row from student table.

```sql
DELETE FROM student
WHERE student_number = "105";
```