## Develop a program that includes the features of nested if-case and case expression. The program can be extended using the null if and coalesce functions.

# Objective: the objective of this program is to use nested if case, case expressions and null if 

```sql
DECLARE
	sno NUMBER(3) :=&sno;
	sname VARCHAR2(20):=’&sname’;
	m1 NUMBER(3) :=&m1;
	m2 NUMBER(3) :=&m2;
	m3 NUMBER(3) :=&m3;
	total NUMBER(4);
	avg1 NUMBER(5,2);
	class VARCHAR(30);
BEGIN
	total :=m1+m2+m3;
	avg1 :=total/3;
	if m1>35 AND m2>35 AND m3>35 then
	if avg1>60 then
	class := 'first class';
end if;

	if avg1>50 AND avg1<60 then
	class := 'second class';
	end if;

	if avg1>40 AND avg1<50 then
	class:= 'third class';
	end if;
	else
	class := 'fail';
	end if;

insert into student(sno,sname,m1,m2,m3,total,avg1,class);
END;
```