### Write a PL/SQL Program using BEFORE and AFTER Triggers – with operations like insert/update/delete which will run on Sundays and all weekdays between 17 pm to 9 am (the following day).

```sql
CREATE OR REPLACE TRIGGER trig1
BEFORE INSERT OR UPDATE OR DELETE ON employee
FOR EACH ROW
DECLARE
    ctime NUMBER := TO_CHAR(SYSDATE, 'hh24');
    cday VARCHAR2(10) := TO_CHAR(SYSDATE, 'day');
BEGIN
    IF (ctime < 9 OR ctime >= 17) THEN
        RAISE_APPLICATION_ERROR(-20002, 'Cannot access data outside permitted hours.');
    END IF;
    
    IF (cday = 'sunday' OR cday = 'SUNDAY') THEN
        RAISE_APPLICATION_ERROR(-20002, 'Cannot access data on Sundays.');
    END IF;
END;
```


```sql
CREATE OR REPLACE TRIGGER trig1_after
AFTER INSERT OR UPDATE OR DELETE ON employee
BEGIN
    DBMS_OUTPUT.PUT_LINE('Operation performed successfully');
END;
```