### Write a PL/SQL Program using stored functions and invoke functions

### Objective: the objective of this program is to create stored, invoke and complex functions.

- Create function which adds two given numbers. (Simple programs)


### Execute the below procedure code first

```sql
CREATE OR REPLACE FUNCTION add_fun(a NUMBER, b NUMBER)
RETURN NUMBER AS
    c NUMBER;
BEGIN
    c := a + b;
    RETURN c;
END;
```


```sql
DECLARE
    result NUMBER;
BEGIN
    result := add_fun(10, 20);
    DBMS_OUTPUT.PUT_LINE('The sum of 10 and 20 is ' || result);
END;
```



### Create a function which count total no.of employees having salary less than 6000

```sql
CREATE OR REPLACE FUNCTION count_emp(esal NUMBER) RETURN NUMBER AS
    cursor vin_cur IS
        SELECT emp_number, emp_sal FROM employee;

    xno employee.emp_number%TYPE;
    xsal employee.emp_sal%TYPE;
    C NUMBER := 0;
BEGIN
    OPEN vin_cur;
    LOOP
        FETCH vin_cur INTO xno, xsal;
        EXIT WHEN vin_cur%NOTFOUND;
        IF xsal < esal THEN
            C := C + 1;
        END IF;
    END LOOP;
    CLOSE vin_cur;
    RETURN C;
END;
```

```sql
DECLARE
    ne NUMBER;
    xsal NUMBER := 6000; -- Set the salary threshold
BEGIN
    ne := count_emp(xsal);
    DBMS_OUTPUT.PUT_LINE('There are ' || ne || ' employees');
END;
```