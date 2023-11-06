# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## Date:

## AIM:
To create a manager database and execute DML queries using SQL.

## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);

```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](update.png)
### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](delete.png)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query3.png)

### Q4)	List the names of Clerks from emp table.

### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query5.png)

### Q5)	List the names of employee who are not Managers.

### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query6.png)

### Q6)	List the names of employees not eligible for commission.

### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query7.png)
### Q7)	List employees whose name either start or end with ‘s’.

### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query8.png)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query9.png)

### Q9) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query10.png)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query11.png)

### Q11) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query12.png)

### Q12) Find number of rows in the table EMP

### QUERY:
```
 select count(*) from manager;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query13.png)

### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:

### MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query14.1.png)
### MINIMUM:
```
select min(salary) from manager;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query14.2.png)
### AVERAGE:
```
select avg(salary) from manager;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query14.3.png)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![EX-2-DATA-MANIPULATION-LANGUAGE-DML-AND-DATA-CONTROL-LANGUAGE-DCL-COMMANDS](query15.png)
### RESULT:
 Therefore,to create a manager database and  DML queries using SQL was executed successfully.
