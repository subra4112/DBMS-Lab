Enter password: *********
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 23
Server version: 8.0.32 MySQL Community Server - GPL

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> create table emp(empid number(4),ename char(10),job char(10),mgid number(4),hiredate date,salary number(4),commission number(4),deptid number(2));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'number(4),ename char(10),job char(10),mgid number(4),hiredate date,salary number' at line 1
mysql> \c
mysql> \c;
ERROR:
No query specified

mysql> CREATE TABLE employees (
    ->   emp_id INT PRIMARY KEY,
    ->   name VARCHAR(20) NOT NULL,
    ->   job VARCHAR(20) NOT NULL,
    ->   manager_id INT,
    ->   hire_date DATE NOT NULL,
    ->   salary INT,
    ->   commission INT,
    ->   dept_id INT NOT NULL
    -> );
ERROR 1046 (3D000): No database selected
mysql> \c
mysql> \c;
ERROR:
No query specified

mysql> use exp1;
Database changed
mysql> CREATE TABLE employees (
    ->   emp_id INT PRIMARY KEY,
    ->   name VARCHAR(20) NOT NULL,
    ->   job VARCHAR(20) NOT NULL,
    ->   manager_id INT,
    ->   hire_date DATE NOT NULL,
    ->   salary INT,
    ->   commission INT,
    ->   dept_id INT NOT NULL
    -> );
Query OK, 0 rows affected (0.05 sec)

mysql> INSERT INTO employees (emp_id, name, job, manager_id, hire_date, salary, commission, dept_id)
    -> VALUES
    ->   (7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800, NULL, 20),
    ->   (7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600, 300, 30),
    ->   (7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250, 500, 30),
    ->   (7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975, NULL, 20),
    ->   (7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250, 1400, 30),
    ->   (7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850, NULL, 30),
    ->   (7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, NULL, 10),
    ->   (7788, 'SCOTT', 'ANALYST', 7566, '1987-04-19', 3000, NULL, 20),
    ->   (7839, 'KING', 'PRESIDENT', NULL, '1981-11-17', 5000, NULL, 10),
    ->   (7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500, 0, 30),
    ->   (7876, 'ADAMS', 'CLERK', 7788, '1987-05-23', 1100, NULL, 20),
    ->   (7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950, NULL, 30),
    ->   (7902, 'FORD', 'ANALYST', 7566, '1981-12-03', 3000, NULL, 20),
    ->   (7934, 'MILLER', 'CLERK', 7782, '1982-01-23', 1300, NULL, 10);
Query OK, 14 rows affected (0.02 sec)
Records: 14  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE dept (
    ->   deptno INT PRIMARY KEY,
    ->   dname VARCHAR(20),
    ->   loc VARCHAR(20)
    -> );
Query OK, 0 rows affected (0.01 sec)

mysql> INSERT INTO dept (deptno, dname, loc)
    -> VALUES
    ->   (10, 'ACCOUNTING', 'NEW YORK'),
    ->   (20, 'RESEARCH', 'DALLAS'),
    ->   (30, 'SALES', 'CHICAGO'),
    ->   (40, 'OPERATIONS', 'BOSTON');
Query OK, 4 rows affected (0.01 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> update dept set loc = 'NEW YORK'
    -> update dept set loc = 'NEW YORK';
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'update dept set loc = 'NEW YORK'' at line 2
mysql> update dept set loc = 'NEW YORK';
Query OK, 3 rows affected (0.01 sec)
Rows matched: 4  Changed: 3  Warnings: 0

mysql> select * from dept
    ->
    -> update dept set loc = 'NEW YORK'
    -> update dept set loc = 'NEW YORK';
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'update dept set loc = 'NEW YORK'
update dept set loc = 'NEW YORK'' at line 3
mysql> select * from dept;
+--------+------------+----------+
| deptno | dname      | loc      |
+--------+------------+----------+
|     10 | ACCOUNTING | NEW YORK |
|     20 | RESEARCH   | NEW YORK |
|     30 | SALES      | NEW YORK |
|     40 | OPERATIONS | NEW YORK |
+--------+------------+----------+
4 rows in set (0.00 sec)

mysql> update dept set loc = 'NEW YORK' for deptno=20;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'for deptno=20' at line 1
mysql> update dept set loc = 'NEW YORK' for deptno = 20;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'for deptno = 20' at line 1
mysql> update dept set loc = 'NEW YORK' where deptno = 20;
Query OK, 0 rows affected (0.01 sec)
Rows matched: 1  Changed: 0  Warnings: 0

mysql> select * from dept;
+--------+------------+----------+
| deptno | dname      | loc      |
+--------+------------+----------+
|     10 | ACCOUNTING | NEW YORK |
|     20 | RESEARCH   | NEW YORK |
|     30 | SALES      | NEW YORK |
|     40 | OPERATIONS | NEW YORK |
+--------+------------+----------+
4 rows in set (0.00 sec)

mysql> delete fro '\c';
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''\c'' at line 1
mysql> '\c'
    ->
    -> hello;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''\c'

hello' at line 1
mysql> delete from exployees where name = 'PAUL';
ERROR 1146 (42S02): Table 'exp1.exployees' doesn't exist
mysql> select * from employees;
+--------+--------+-----------+------------+------------+--------+------------+---------+
| emp_id | name   | job       | manager_id | hire_date  | salary | commission | dept_id |
+--------+--------+-----------+------------+------------+--------+------------+---------+
|   7369 | SMITH  | CLERK     |       7902 | 1980-12-17 |    800 |       NULL |      20 |
|   7499 | ALLEN  | SALESMAN  |       7698 | 1981-02-20 |   1600 |        300 |      30 |
|   7521 | WARD   | SALESMAN  |       7698 | 1981-02-22 |   1250 |        500 |      30 |
|   7566 | JONES  | MANAGER   |       7839 | 1981-04-02 |   2975 |       NULL |      20 |
|   7654 | MARTIN | SALESMAN  |       7698 | 1981-09-28 |   1250 |       1400 |      30 |
|   7698 | BLAKE  | MANAGER   |       7839 | 1981-05-01 |   2850 |       NULL |      30 |
|   7782 | CLARK  | MANAGER   |       7839 | 1981-06-09 |   2450 |       NULL |      10 |
|   7788 | SCOTT  | ANALYST   |       7566 | 1987-04-19 |   3000 |       NULL |      20 |
|   7839 | KING   | PRESIDENT |       NULL | 1981-11-17 |   5000 |       NULL |      10 |
|   7844 | TURNER | SALESMAN  |       7698 | 1981-09-08 |   1500 |
0 |      30 |
|   7876 | ADAMS  | CLERK     |       7788 | 1987-05-23 |   1100 |       NULL |      20 |
|   7900 | JAMES  | CLERK     |       7698 | 1981-12-03 |    950 |       NULL |      30 |
|   7902 | FORD   | ANALYST   |       7566 | 1981-12-03 |   3000 |       NULL |      20 |
|   7934 | MILLER | CLERK     |       7782 | 1982-01-23 |   1300 |       NULL |      10 |
+--------+--------+-----------+------------+------------+--------+------------+---------+
14 rows in set (0.00 sec)

mysql>  delete from exployees where name = 'PAUL';
ERROR 1146 (42S02): Table 'exp1.exployees' doesn't exist
mysql>  delete from employees where name = 'PAUL';
Query OK, 0 rows affected (0.00 sec)

mysql> select * from employees;
+--------+--------+-----------+------------+------------+--------+------------+---------+
| emp_id | name   | job       | manager_id | hire_date  | salary | commission | dept_id |
+--------+--------+-----------+------------+------------+--------+------------+---------+
|   7369 | SMITH  | CLERK     |       7902 | 1980-12-17 |    800 |       NULL |      20 |
|   7499 | ALLEN  | SALESMAN  |       7698 | 1981-02-20 |   1600 |        300 |      30 |
|   7521 | WARD   | SALESMAN  |       7698 | 1981-02-22 |   1250 |        500 |      30 |
|   7566 | JONES  | MANAGER   |       7839 | 1981-04-02 |   2975 |       NULL |      20 |
|   7654 | MARTIN | SALESMAN  |       7698 | 1981-09-28 |   1250 |       1400 |      30 |
|   7698 | BLAKE  | MANAGER   |       7839 | 1981-05-01 |   2850 |       NULL |      30 |
|   7782 | CLARK  | MANAGER   |       7839 | 1981-06-09 |   2450 |       NULL |      10 |
|   7788 | SCOTT  | ANALYST   |       7566 | 1987-04-19 |   3000 |       NULL |      20 |
|   7839 | KING   | PRESIDENT |       NULL | 1981-11-17 |   5000 |       NULL |      10 |
|   7844 | TURNER | SALESMAN  |       7698 | 1981-09-08 |   1500 |
0 |      30 |
|   7876 | ADAMS  | CLERK     |       7788 | 1987-05-23 |   1100 |       NULL |      20 |
|   7900 | JAMES  | CLERK     |       7698 | 1981-12-03 |    950 |       NULL |      30 |
|   7902 | FORD   | ANALYST   |       7566 | 1981-12-03 |   3000 |       NULL |      20 |
|   7934 | MILLER | CLERK     |       7782 | 1982-01-23 |   1300 |       NULL |      10 |
+--------+--------+-----------+------------+------------+--------+------------+---------+
14 rows in set (0.00 sec)

mysql> select employees.name, dept.salary;
ERROR 1109 (42S02): Unknown table 'employees' in field list
mysql> select salary from dept;
ERROR 1054 (42S22): Unknown column 'salary' in 'field list'
mysql> select name,salary from employees;
+--------+--------+
| name   | salary |
+--------+--------+
| SMITH  |    800 |
| ALLEN  |   1600 |
| WARD   |   1250 |
| JONES  |   2975 |
| MARTIN |   1250 |
| BLAKE  |   2850 |
| CLARK  |   2450 |
| SCOTT  |   3000 |
| KING   |   5000 |
| TURNER |   1500 |
| ADAMS  |   1100 |
| JAMES  |    950 |
| FORD   |   3000 |
| MILLER |   1300 |
+--------+--------+
14 rows in set (0.00 sec)

mysql> select distinct dname from dept;
+------------+
| dname      |
+------------+
| ACCOUNTING |
| RESEARCH   |
| SALES      |
| OPERATIONS |
+------------+
4 rows in set (0.01 sec)

mysql> select name from employees where empid = 7788;
ERROR 1054 (42S22): Unknown column 'empid' in 'where clause'
mysql>  select name from employees where emp_id = 7788;
+-------+
| name  |
+-------+
| SCOTT |
+-------+
1 row in set (0.01 sec)

mysql> SELECT ename as name, sal salary FROM employees;
ERROR 1054 (42S22): Unknown column 'ename' in 'field list'
mysql> select name as ename,salary as sal from employees;
+--------+------+
| ename  | sal  |
+--------+------+
| SMITH  |  800 |
| ALLEN  | 1600 |
| WARD   | 1250 |
| JONES  | 2975 |
| MARTIN | 1250 |
| BLAKE  | 2850 |
| CLARK  | 2450 |
| SCOTT  | 3000 |
| KING   | 5000 |
| TURNER | 1500 |
| ADAMS  | 1100 |
| JAMES  |  950 |
| FORD   | 3000 |
| MILLER | 1300 |
+--------+------+
14 rows in set (0.00 sec)

mysql> SELECT id, first_name, last_name
    -> FROM customer
    ->
    -> ;
ERROR 1146 (42S02): Table 'exp1.customer' doesn't exist
mysql> SELECT id, first_name, last_name
    -> FROM customer
    ->   (7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, NULL, 10),;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '(7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, NULL, 10),' at line 3
mysql> SELECT id, first_name, last_name
    -> FROM customer
    -> FROM customer;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'FROM customer' at line 3
mysql> SELECT id, first_name, last_name
    -> FROM customer
    -> INTO OUTFILE '/temp/myoutput.txt';
ERROR 1146 (42S02): Table 'exp1.customer' doesn't exist
mysql>
