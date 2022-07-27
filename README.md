# Basic_SQL

ubuntu@ubuntu-OptiPlex-5000:~$ mysql --version
mysql  Ver 8.0.29-0ubuntu0.22.04.2 for Linux on x86_64 ((Ubuntu))
ubuntu@ubuntu-OptiPlex-5000:~$ mysql -u root p
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: NO)
ubuntu@ubuntu-OptiPlex-5000:~$ mysql -u root -p
Enter password: 
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
ubuntu@ubuntu-OptiPlex-5000:~$ mysql -u root -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 8.0.29-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2022, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> create database stu_info;
Query OK, 1 row affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| Movies             |
| STUDENT            |
| information_schema |
| mysql              |
| performance_schema |
| stu_info           |
| sys                |
+--------------------+
7 rows in set (0.00 sec)

mysql> use stu_info;
Database changed
mysql> create table stu_info;
ERROR 4028 (HY000): A table must have at least one visible column.
mysql> create database employee;
Query OK, 1 row affected (0.02 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| Movies             |
| STUDENT            |
| employee           |
| information_schema |
| mysql              |
| performance_schema |
| stu_info           |
| sys                |
+--------------------+
8 rows in set (0.00 sec)

mysql> use employee;
Database changed
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '(10))' at line 1
mysql> create table employee (Emp_ID int(10), Emp_Name varchar(15), Emp_City(10));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '(10))' at line 1
mysql> create table employee (Emp_ID int(10), Emp_Name varchar(15), Emp_City varchar(15));
Query OK, 0 rows affected, 1 warning (0.04 sec)

mysql> show table;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> show tables;
+--------------------+
| Tables_in_employee |
+--------------------+
| employee           |
+--------------------+
1 row in set (0.00 sec)

mysql> insert into employee values (111, "Tejas", "Pune");
Query OK, 1 row affected (0.01 sec)

mysql> show tables;
+--------------------+
| Tables_in_employee |
+--------------------+
| employee           |
+--------------------+
1 row in set (0.00 sec)

mysql> select * from employee;
+--------+----------+----------+
| Emp_ID | Emp_Name | Emp_City |
+--------+----------+----------+
|    111 | Tejas    | Pune     |
+--------+----------+----------+
1 row in set (0.00 sec)

mysql> drop table employee;
Query OK, 0 rows affected (0.03 sec)

mysql> select * from employee;
ERROR 1146 (42S02): Table 'employee.employee' doesn't exist
mysql> show tables;
Empty set (0.00 sec)

mysql> insert into employee values (112, "Viraj", "Nagar");
ERROR 1146 (42S02): Table 'employee.employee' doesn't exist
mysql> create table employee(^C
mysql> create table employee (Emp_ID int(10), Emp_Name varchar(15), Emp_City(10));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '(10))' at line 1
mysql> create table employee (Emp_ID int(10), Emp_Name varchar(15), Emp_City varchar(10));
Query OK, 0 rows affected, 1 warning (0.04 sec)

mysql> show tables;
+--------------------+
| Tables_in_employee |
+--------------------+
| employee           |
+--------------------+
1 row in set (0.00 sec)

mysql> insert into employee values (111, "Tejas", "Pune");
Query OK, 1 row affected (0.02 sec)

mysql> select * from employee;
+--------+----------+----------+
| Emp_ID | Emp_Name | Emp_City |
+--------+----------+----------+
|    111 | Tejas    | Pune     |
+--------+----------+----------+
1 row in set (0.00 sec)

Query OK, 3 rows affected (0.03 sec)112, "Viraj", "Nagar"), (113, "Himanshu", "Pune"),(114, "Affan", "Nandurbar");
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from employee;
+--------+----------+-----------+
| Emp_ID | Emp_Name | Emp_City  |
+--------+----------+-----------+
|    111 | Tejas    | Pune      |
|    112 | Viraj    | Nagar     |
|    113 | Himanshu | Pune      |
|    114 | Affan    | Nandurbar |
+--------+----------+-----------+
4 rows in set (0.00 sec)

mysql> alter table employee add column mobile_no int;
Query OK, 0 rows affected (0.03 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> select * from employee;
+--------+----------+-----------+-----------+
| Emp_ID | Emp_Name | Emp_City  | mobile_no |
+--------+----------+-----------+-----------+
|    111 | Tejas    | Pune      |      NULL |
|    112 | Viraj    | Nagar     |      NULL |
|    113 | Himanshu | Pune      |      NULL |
|    114 | Affan    | Nandurbar |      NULL |
+--------+----------+-----------+-----------+
4 rows in set (0.01 sec)

mysql> alter table employee add column mobile_no;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> alter table employee drop column mobile_no;
Query OK, 0 rows affected (0.04 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> select * from employee;
+--------+----------+-----------+
| Emp_ID | Emp_Name | Emp_City  |
+--------+----------+-----------+
|    111 | Tejas    | Pune      |
|    112 | Viraj    | Nagar     |
|    113 | Himanshu | Pune      |
|    114 | Affan    | Nandurbar |
+--------+----------+-----------+
4 rows in set (0.00 sec)

mysql> alter table employee add column mobile_no int;
Query OK, 0 rows affected (0.03 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> select * from employee;
+--------+----------+-----------+-----------+
| Emp_ID | Emp_Name | Emp_City  | mobile_no |
+--------+----------+-----------+-----------+
|    111 | Tejas    | Pune      |      NULL |
|    112 | Viraj    | Nagar     |      NULL |
|    113 | Himanshu | Pune      |      NULL |
|    114 | Affan    | Nandurbar |      NULL |
+--------+----------+-----------+-----------+
4 rows in set (0.00 sec)

mysql> alter table employee rename column mobile_no mobile_nos int;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'mobile_nos int' at line 1
mysql> alter table employee rename column mobile_no mobile_nos;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'mobile_nos' at line 1
mysql> alter table employee rename column mobile_no to mobile_nos;
Query OK, 0 rows affected (0.01 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> select * from employee;
+--------+----------+-----------+------------+
| Emp_ID | Emp_Name | Emp_City  | mobile_nos |
+--------+----------+-----------+------------+
|    111 | Tejas    | Pune      |       NULL |
|    112 | Viraj    | Nagar     |       NULL |
|    113 | Himanshu | Pune      |       NULL |
|    114 | Affan    | Nandurbar |       NULL |
+--------+----------+-----------+------------+
4 rows in set (0.00 sec)

mysql> alter table employee modify column Emp_ID varchar(10);
Query OK, 4 rows affected (0.06 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from employee;
+--------+----------+-----------+------------+
| Emp_ID | Emp_Name | Emp_City  | mobile_nos |
+--------+----------+-----------+------------+
| 111    | Tejas    | Pune      |       NULL |
| 112    | Viraj    | Nagar     |       NULL |
| 113    | Himanshu | Pune      |       NULL |
| 114    | Affan    | Nandurbar |       NULL |
+--------+----------+-----------+------------+
4 rows in set (0.00 sec)

mysql> desc employee;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| Emp_ID     | varchar(10) | YES  |     | NULL    |       |
| Emp_Name   | varchar(15) | YES  |     | NULL    |       |
| Emp_City   | varchar(10) | YES  |     | NULL    |       |
| mobile_nos | int         | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> select * from employeewhere Emp_ID=200;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '=200' at line 1
mysql> select * from employee where Emp_ID=200;
Empty set (0.00 sec)

mysql> select * from employee where Emp_ID=111;
+--------+----------+----------+------------+
| Emp_ID | Emp_Name | Emp_City | mobile_nos |
+--------+----------+----------+------------+
| 111    | Tejas    | Pune     |       NULL |
+--------+----------+----------+------------+
1 row in set (0.00 sec)

mysql> select * from employee where Emp_ID="111";
+--------+----------+----------+------------+
| Emp_ID | Emp_Name | Emp_City | mobile_nos |
+--------+----------+----------+------------+
| 111    | Tejas    | Pune     |       NULL |
+--------+----------+----------+------------+
1 row in set (0.00 sec)

mysql> update employee set mob_nos=1234567890 where Emp_ID=111;
ERROR 1054 (42S22): Unknown column 'mob_nos' in 'field list'
mysql> update employee set mobile_nos=1234567890 where Emp_ID=111;
Query OK, 1 row affected (0.03 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from employee;
+--------+----------+-----------+------------+
| Emp_ID | Emp_Name | Emp_City  | mobile_nos |
+--------+----------+-----------+------------+
| 111    | Tejas    | Pune      | 1234567890 |
| 112    | Viraj    | Nagar     |       NULL |
| 113    | Himanshu | Pune      |       NULL |
| 114    | Affan    | Nandurbar |       NULL |
+--------+----------+-----------+------------+
4 rows in set (0.00 sec)

mysql> create table asd;
ERROR 4028 (HY000): A table must have at least one visible column.
mysql> create table asd(ID int(10), Name varchar(10), mob_no(10));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '(10))' at line 1
mysql> create table asd(ID int(10), Name varchar(10), mob_no int(10));
Query OK, 0 rows affected, 2 warnings (0.04 sec)

mysql> select * from asd;
Empty set (0.01 sec)

mysql> insert into asd values(111, "Viraj", 98877);
Query OK, 1 row affected (0.02 sec)

mysql> select * from asd;
+------+-------+--------+
| ID   | Name  | mob_no |
+------+-------+--------+
|  111 | Viraj |  98877 |
+------+-------+--------+
1 row in set (0.00 sec)

mysql> insert into asd values(112, "Sweta", 9887798877);
ERROR 1264 (22003): Out of range value for column 'mob_no' at row 1
mysql> alter table asd modify column mob_no long(10);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '(10)' at line 1
mysql> alter table asd modify column mob_no long;
Query OK, 1 row affected (0.05 sec)
Records: 1  Duplicates: 0  Warnings: 0

mysql> select * from asd;
+------+-------+--------+
| ID   | Name  | mob_no |
+------+-------+--------+
|  111 | Viraj | 98877  |
+------+-------+--------+
1 row in set (0.00 sec)

mysql> insert into asd values(112, "Sweta", 9887798877);
Query OK, 1 row affected (0.02 sec)

mysql> select * from asd;
+------+-------+------------+
| ID   | Name  | mob_no     |
+------+-------+------------+
|  111 | Viraj | 98877      |
|  112 | Sweta | 9887798877 |
+------+-------+------------+
2 rows in set (0.00 sec)

mysql> insert into asd values(ppp, "Bond", 9886698866);
ERROR 1054 (42S22): Unknown column 'ppp' in 'field list'
