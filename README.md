# basic-and-advanced-sql
Microsoft Windows [Version 10.0.19045.3208]
(c) Microsoft Corporation. All rights reserved.

C:\Users\SAIKIRAN>cd/

C:\>cd xampp

C:\xampp>cd mysql

C:\xampp\mysql>cd bin

C:\xampp\mysql\bin>mysql.exe -u root;
ERROR 1045 (28000): Access denied for user 'root;'@'localhost' (using password: NO)

C:\xampp\mysql\bin>mysql.exe -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.24-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| aaaa               |
| collage            |
| company            |
| info               |
| information_schema |
| mysql              |
| pavan              |
| performance_schema |
| phpmyadmin         |
| student            |
| studentinfo        |
| test               |
| vishnu             |
+--------------------+
13 rows in set (0.058 sec)

MariaDB [(none)]> use collage;
Database changed
MariaDB [collage]> create table data(id int primary key,name varchar(20),age int);
ERROR 1050 (42S01): Table 'data' already exists
MariaDB [collage]> desc data;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(11)     | NO   | PRI | NULL    |       |
| name  | varchar(20) | YES  |     | NULL    |       |
| age   | int(11)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.173 sec)

MariaDB [collage]>  insert into data(id,name,age)values(1001,'sai',18);
ERROR 1062 (23000): Duplicate entry '1001' for key 'PRIMARY'
MariaDB [collage]>  insert into data(id,name,age)values(1001,'sai',18);
ERROR 1062 (23000): Duplicate entry '1001' for key 'PRIMARY'
MariaDB [collage]> insertt into data(id,name,age)values(1001,'sai',18);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'insertt into data(id,name,age)values(1001,'sai',18)' at line 1
MariaDB [collage]> insert into data(id,name,age)values(1001,'sai',18);
ERROR 1062 (23000): Duplicate entry '1001' for key 'PRIMARY'
MariaDB [collage]> insert into data(id,name,age)values(1002,'sai',18);
Query OK, 1 row affected (0.021 sec)

MariaDB [collage]>  insert into data(id,name,age)values(1092,'ram',21);
ERROR 1062 (23000): Duplicate entry '1092' for key 'PRIMARY'
MariaDB [collage]>  insert into data(id,name,age)values(1004,'ram',21);
Query OK, 1 row affected (0.005 sec)

MariaDB [collage]>  insert into data(id,name,age)values(1006,'ram',21);
Query OK, 1 row affected (0.007 sec)

MariaDB [collage]> insert into data(id,name,age)values(1010,'vani',19);
Query OK, 1 row affected (0.006 sec)

MariaDB [collage]> desc data;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(11)     | NO   | PRI | NULL    |       |
| name  | varchar(20) | YES  |     | NULL    |       |
| age   | int(11)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.035 sec)

MariaDB [collage]> select*from data;
+------+------+------+
| id   | name | age  |
+------+------+------+
| 1001 | sai  |   18 |
| 1002 | sai  |   18 |
| 1004 | ram  |   21 |
| 1006 | ram  |   21 |
| 1010 | vani |   19 |
| 1011 | vani |   19 |
| 1023 | hari |   19 |
| 1092 | ram  |   21 |
+------+------+------+
8 rows in set (0.012 sec)

MariaDB [collage]>  select*from data where name like '%hello%';
Empty set (0.012 sec)

MariaDB [collage]> seelect*from data where age=18;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'seelect*from data where age=18' at line 1
MariaDB [collage]> select*from data where age=18;
+------+------+------+
| id   | name | age  |
+------+------+------+
| 1001 | sai  |   18 |
| 1002 | sai  |   18 |
+------+------+------+
2 rows in set (0.007 sec)

MariaDB [collage]>  select*from data where name like '%vani%';
+------+------+------+
| id   | name | age  |
+------+------+------+
| 1010 | vani |   19 |
| 1011 | vani |   19 |
+------+------+------+
2 rows in set (0.000 sec)

MariaDB [collage]> create database storesales;
Query OK, 1 row affected (0.011 sec)

MariaDB [collage]> use storesales;
Database changed
MariaDB [storesales]> create table mysales (month varchar(15), prod_name  varchar(15), sales int );
Query OK, 0 rows affected (0.176 sec)

MariaDB [storesales]> desc mysales;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| month     | varchar(15) | YES  |     | NULL    |       |
| prod_name | varchar(15) | YES  |     | NULL    |       |
| sales     | int(11)     | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
3 rows in set (0.029 sec)

MariaDB [storesales]> insert into mysales values('Jan', 'Fruits', 45000), ('Jan', 'Vegetables', 67000), ('Jan', 'Dairy', 55000), ('Feb', 'Fruits', 42000), ('Feb', 'Vegetables', 32000), ('Feb', 'Dairy', 52000), ('March', 'Fruits', 61000), ('March', 'Vegetables', 43000));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near ')' at line 1
MariaDB [storesales]> insert into mysales values('Jan', 'Fruits', 45000), ('Jan', 'Vegetables', 67000), ('Jan', 'Dairy', 55000), ('Feb', 'Fruits', 42000), ('Feb', 'Vegetables', 32000), ('Feb', 'Dairy', 52000), ('March', 'Fruits', 61000), ('March', 'Vegetables', 43000);
Query OK, 8 rows affected (0.011 sec)
Records: 8  Duplicates: 0  Warnings: 0

MariaDB [storesales]> show mysales;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'mysales' at line 1
MariaDB [storesales]> desc mysales;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| month     | varchar(15) | YES  |     | NULL    |       |
| prod_name | varchar(15) | YES  |     | NULL    |       |
| sales     | int(11)     | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
3 rows in set (0.027 sec)

MariaDB [storesales]> select*from mysales;
+-------+------------+-------+
| month | prod_name  | sales |
+-------+------------+-------+
| Jan   | Fruits     | 45000 |
| Jan   | Vegetables | 67000 |
| Jan   | Dairy      | 55000 |
| Feb   | Fruits     | 42000 |
| Feb   | Vegetables | 32000 |
| Feb   | Dairy      | 52000 |
| March | Fruits     | 61000 |
| March | Vegetables | 43000 |
+-------+------------+-------+
8 rows in set (0.001 sec)

MariaDB [storesales]> select count from mysales;
ERROR 1054 (42S22): Unknown column 'count' in 'field list'
MariaDB [storesales]> select count(month) from mysales;
+--------------+
| count(month) |
+--------------+
|            8 |
+--------------+
1 row in set (0.013 sec)

MariaDB [storesales]> select sum(month) from mysales;
+------------+
| sum(month) |
+------------+
|          0 |
+------------+
1 row in set, 8 warnings (0.005 sec)

MariaDB [storesales]> select sum(sales) from mysales;
+------------+
| sum(sales) |
+------------+
|     397000 |
+------------+
1 row in set (0.005 sec)

MariaDB [storesales]> select avg(sales) from mysales;
+------------+
| avg(sales) |
+------------+
| 49625.0000 |
+------------+
1 row in set (0.004 sec)

MariaDB [storesales]> select min(sales) from mysales;
+------------+
| min(sales) |
+------------+
|      32000 |
+------------+
1 row in set (0.004 sec)

MariaDB [storesales]> select max(sales) from mysales;
+------------+
| max(sales) |
+------------+
|      67000 |
+------------+
1 row in set (0.004 sec)

MariaDB [storesales]> select month, avg(sales) from mysales group by month;
+-------+------------+
| month | avg(sales) |
+-------+------------+
| Feb   | 42000.0000 |
| Jan   | 55666.6667 |
| March | 52000.0000 |
+-------+------------+
3 rows in set (0.018 sec)

MariaDB [storesales]> select prod_name, avg(sales) from mysales group by month;
+-----------+------------+
| prod_name | avg(sales) |
+-----------+------------+
| Fruits    | 42000.0000 |
| Fruits    | 55666.6667 |
| Fruits    | 52000.0000 |
+-----------+------------+
3 rows in set (0.001 sec)

MariaDB [storesales]> select prod_name=vegetables, avg(sales) from mysales group by month;
ERROR 1054 (42S22): Unknown column 'vegetables' in 'field list'
MariaDB [storesales]> select prod_name=vegetables, avg(sales) from mysales group by prod_name;
ERROR 1054 (42S22): Unknown column 'vegetables' in 'field list'
MariaDB [storesales]> select prod_name, avg(sales) from mysales group by prod_name;
+------------+------------+
| prod_name  | avg(sales) |
+------------+------------+
| Dairy      | 53500.0000 |
| Fruits     | 49333.3333 |
| Vegetables | 47333.3333 |
+------------+------------+
3 rows in set (0.010 sec)

MariaDB [storesales]> select now();
+---------------------+
| now()               |
+---------------------+
| 2023-08-03 19:18:22 |
+---------------------+
1 row in set (0.006 sec)

MariaDB [storesales]> select curdate();
+------------+
| curdate()  |
+------------+
| 2023-08-03 |
+------------+
1 row in set (0.023 sec)

MariaDB [storesales]> select date_format(curdate(), '%m/%d/%Y') today;
+------------+
| today      |
+------------+
| 08/03/2023 |
+------------+
1 row in set (0.011 sec)

MariaDB [storesales]> create tables SalesOrders ( id integer,  CustomerID Integer,    OrderDate Date,    FinancialCode Char( 2 ),    Region Char( 7 ),    SalesRepresentative Integer);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'tables SalesOrders ( id integer,  CustomerID Integer,    OrderDate Date,    F...' at line 1
MariaDB [storesales]> create tables inform(id int(10),name varchar(10),customerid int(10),orderdate intger,orderamount int(20));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'tables inform(id int(10),name varchar(10),customerid int(10),orderdate intger...' at line 1
MariaDB [storesales]> create table inform(id int(10),name varchar(10),customerid int(10),orderdate intger,orderamount int(20));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'orderamount int(20))' at line 1
MariaDB [storesales]> create table inform(id int(10),name varchar(10),customerid int(10),orderdate int(10),orderamount int(20));
Query OK, 0 rows affected (0.198 sec)

MariaDB [storesales]> desc inform;
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| id          | int(10)     | YES  |     | NULL    |       |
| name        | varchar(10) | YES  |     | NULL    |       |
| customerid  | int(10)     | YES  |     | NULL    |       |
| orderdate   | int(10)     | YES  |     | NULL    |       |
| orderamount | int(20)     | YES  |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
5 rows in set (0.043 sec)

MariaDB [storesales]> insert into inform values(2001,'laila',4673,'june',2999);
Query OK, 1 row affected, 1 warning (0.018 sec)

MariaDB [storesales]> insert into inform values(2002,'hari',7468,'march',2433);
Query OK, 1 row affected, 1 warning (0.008 sec)

MariaDB [storesales]> insert into inform values(2003,'nandhini',3748,'april',1676);
Query OK, 1 row affected, 1 warning (0.004 sec)

MariaDB [storesales]> select*from inform;
+------+----------+------------+-----------+-------------+
| id   | name     | customerid | orderdate | orderamount |
+------+----------+------------+-----------+-------------+
| 2001 | laila    |       4673 |         0 |        2999 |
| 2002 | hari     |       7468 |         0 |        2433 |
| 2003 | nandhini |       3748 |         0 |        1676 |
+------+----------+------------+-----------+-------------+
3 rows in set (0.001 sec)

MariaDB [storesales]> select * from inform where orderamount between '1000' and '2000';
+------+----------+------------+-----------+-------------+
| id   | name     | customerid | orderdate | orderamount |
+------+----------+------------+-----------+-------------+
| 2003 | nandhini |       3748 |         0 |        1676 |
+------+----------+------------+-----------+-------------+
1 row in set (0.004 sec)

MariaDB [storesales]> create table matter(id int(10),name varchar
    -> create table matter(id int(10),name varchar(10));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'create table matter(id int(10),name varchar(10))' at line 2
MariaDB [storesales]> create table matter(id int(10),name varchar(10),customerid int(10),orderdate int(10),orderamount int(10));
Query OK, 0 rows affected (0.082 sec)

MariaDB [storesales]> desc matter;
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| id          | int(10)     | YES  |     | NULL    |       |
| name        | varchar(10) | YES  |     | NULL    |       |
| customerid  | int(10)     | YES  |     | NULL    |       |
| orderdate   | int(10)     | YES  |     | NULL    |       |
| orderamount | int(10)     | YES  |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
5 rows in set (0.026 sec)

MariaDB [storesales]> insert into matter values(2005,'shiva',3847,10-2-2023,192);
Query OK, 1 row affected (0.010 sec)

MariaDB [storesales]> insert into matter values(2009,'venu',2849,20-5-2023,26000);
Query OK, 1 row affected (0.004 sec)

MariaDB [storesales]> insert into matter values(2012,'lord',2989,22-6-2023,348);
Query OK, 1 row affected (0.004 sec)

MariaDB [storesales]> insert into matter values(2016,'maya',3002,27-6-2023,1409);
Query OK, 1 row affected (0.005 sec)

MariaDB [storesales]> select*from matter;
+------+-------+------------+-----------+-------------+
| id   | name  | customerid | orderdate | orderamount |
+------+-------+------------+-----------+-------------+
| 2005 | shiva |       3847 |     -2015 |         192 |
| 2009 | venu  |       2849 |     -2008 |       26000 |
| 2012 | lord  |       2989 |     -2007 |         348 |
| 2016 | maya  |       3002 |     -2002 |        1409 |
+------+-------+------------+-----------+-------------+
4 rows in set (0.001 sec)

MariaDB [storesales]> select*from inform union select*from matter;
+------+----------+------------+-----------+-------------+
| id   | name     | customerid | orderdate | orderamount |
+------+----------+------------+-----------+-------------+
| 2001 | laila    |       4673 |         0 |        2999 |
| 2002 | hari     |       7468 |         0 |        2433 |
| 2003 | nandhini |       3748 |         0 |        1676 |
| 2005 | shiva    |       3847 |     -2015 |         192 |
| 2009 | venu     |       2849 |     -2008 |       26000 |
| 2012 | lord     |       2989 |     -2007 |         348 |
| 2016 | maya     |       3002 |     -2002 |        1409 |
+------+----------+------------+-----------+-------------+
7 rows in set (0.010 sec)

MariaDB [storesales]> insert into matter values(2001,'laila',4673,0,2999);
Query OK, 1 row affected (0.004 sec)

MariaDB [storesales]> select * from inform where inform.Customerid in (select matter.Customerid from matter);
+------+-------+------------+-----------+-------------+
| id   | name  | customerid | orderdate | orderamount |
+------+-------+------------+-----------+-------------+
| 2001 | laila |       4673 |         0 |        2999 |
+------+-------+------------+-----------+-------------+
1 row in set (0.014 sec)

MariaDB [storesales]>

