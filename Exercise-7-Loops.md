## Write a Program using loop, while loops, for loops along with error handling and user defined exceptions.

## Write a program to generate first 10 natural numbers using loop, while and for

### Using loop statement

```sql
declare
	I number;

begin
	I:=1;

loop
	dbms_output.put_line(I);
	I:=I+1;
	exit when I>10;
end loop;
end;
```

### Using while

```sql
declare
	I number;
	
begin
	I:=1;
	
while (I<=10)
	loop
	dbms_output.put_line (I);
	I:=I+1;
	end loop;
end;
```


### Using for loop

```sql
DECLARE
    I NUMBER;
BEGIN
    FOR I IN 1..10 LOOP
        DBMS_OUTPUT.PUT_LINE(I);
    END LOOP;
END;
```


### Program using predefined exceptions.

```sql
declare
  emp_number employee.emp_number%type= &number;
  name employee.emp_name%type;

begin
  select emp_name into name from employee
  where emp_number=emp_number;

exception when NO_DATA_FOUND then
  dbms_output.put_line(‘no such employee’);
end;
```

Expected Output:
number: 1001
sureash