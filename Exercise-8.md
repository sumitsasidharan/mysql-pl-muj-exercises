## Write a PL/SQL Program to create i to create procedures ii pass parameters IN & OUT.

### Objective: the objective of this program is to create procedure using IN-OUT parameters. Create a procedure using IN parameter

```sql
create or replace procedure p1 (eno IN number,employee_name varchar)
as
begin
update employee set employee_name=employee_name where
emp_number = eno;
end;
```

Expected Output:
Passing values to parameters
exec p1(1003,’ramya’);

### create a procedure using OUT parameter

```sql
Create procedure p2(p2 emp_number int, p2 emp_deptno out int)
is

begin
select depino
into emp_dept
from employee
where emp_number=emp_number;
end;
```


Expected Output:
Functionally, the code above may be used as in this example:
EXEC P2(1002,:emp_deptno);
PL/SQL procedure successfully completed.
PRINT emp_deptno;
Emp_deptno
