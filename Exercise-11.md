### Write a PL/ SQL cursor program to fetch first three records of an employee table

```sql
DECLARE
    CURSOR c2 IS
        SELECT * FROM employee;
    erec employee%ROWTYPE;
    counter NUMBER := 0;
BEGIN
    OPEN c2;
    LOOP
        FETCH c2 INTO erec;
        EXIT WHEN c2%NOTFOUND OR counter >= 3;

        DBMS_OUTPUT.PUT_LINE('------------');
        DBMS_OUTPUT.PUT_LINE('emp_number: ' || erec.emp_number);
        DBMS_OUTPUT.PUT_LINE('emp_name: ' || erec.emp_name);

        counter := counter + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('------------');
    DBMS_OUTPUT.PUT_LINE('no. of employees: ' || counter);

    CLOSE c2;
END;
```
