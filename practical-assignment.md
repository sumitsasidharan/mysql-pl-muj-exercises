
## SQL QUERIES

### 1. Display worker name, getting highest salary

```sql
SELECT NAME
FROM Worker
WHERE SALARY = (SELECT MAX(SALARY) FROM Worker);
```


### 2. Display names of all workers in descending order.

```sql
SELECT NAME
FROM Worker
ORDER BY NAME DESC;
```


### 3. Display workers name with the count of workers having similar names

```sql
SELECT NAME, COUNT(*) AS COUNT
FROM Worker
GROUP BY NAME
ORDER BY COUNT DESC;
```



## PL / SQL PROGRAMS

### 4. Swap two numbers

```sql
DECLARE
  a NUMBER := 2;
  b NUMBER := 5;
  temp NUMBER;
  
BEGIN
  DBMS_OUTPUT.PUT_LINE('Before swapping:');
  DBMS_OUTPUT.PUT_LINE('a = ' || a);
  DBMS_OUTPUT.PUT_LINE('b = ' || b);

  temp := a;
  a := b;
  b := temp;

  DBMS_OUTPUT.PUT_LINE('After swapping:');
  DBMS_OUTPUT.PUT_LINE('a = ' || a);
  DBMS_OUTPUT.PUT_LINE('b = ' || b);
END;
```

### 5. Check if a number is palindrome.

```sql
DECLARE
  n INT := 121;
  reversedNumber INT := 0;
  remainder INT;

BEGIN
  DECLARE
    originalNumber INT := n;
  BEGIN
    WHILE n > 0 LOOP
      remainder := MOD(n, 10);
      reversedNumber := reversedNumber * 10 + remainder;
      n := TRUNC(n / 10);
    END LOOP;

    IF originalNumber = reversedNumber THEN
      DBMS_OUTPUT.PUT_LINE('Palindrome.');
    ELSE
      DBMS_OUTPUT.PUT_LINE('Not Palindrome.');
    END IF;
  END;
END;
```