Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 12406550
Server version: 8.0.40 Source distribution

Copyright (c) 2000, 2022, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show tables;
+---------------------------------+
| Tables_in_emmasanchez35$default |
+---------------------------------+
| detalle_horario                 |
| horario                         |
| plantilla_detalle_horario       |
+---------------------------------+
3 rows in set (0.00 sec)

mysql> desc detalle_horario;
+--------------------+-------------+------+-----+---------+-------+
| Field              | Type        | Null | Key | Default | Extra |
+--------------------+-------------+------+-----+---------+-------+
| horario_id         | int         | NO   | PRI | NULL    |       |
| hora_salida        | date        | NO   | PRI | NULL    |       |
| hora_entrada       | date        | NO   |     | NULL    |       |
| codigo_incapacidad | varchar(25) | YES  |     | NULL    |       |
+--------------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> desc horario;
+--------------+------+------+-----+---------+----------------+
| Field        | Type | Null | Key | Default | Extra          |
+--------------+------+------+-----+---------+----------------+
| horario_id   | int  | NO   | PRI | NULL    | auto_increment |
| plantilla_id | int  | YES  |     | NULL    |                |
+--------------+------+------+-----+---------+----------------+
2 rows in set (0.00 sec)

mysql> desc plantilla_detalle_horario;
+--------------------+-------------+------+-----+---------+-------+
| Field              | Type        | Null | Key | Default | Extra |
+--------------------+-------------+------+-----+---------+-------+
| plantilla_id       | int         | NO   | PRI | NULL    |       |
| dia                | int         | NO   | PRI | NULL    |       |
| codigo_incapacidad | varchar(25) | YES  |     | NULL    |       |
| turno              | varchar(25) | YES  |     | NULL    |       |
+--------------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> select * from horario;
+------------+--------------+
| horario_id | plantilla_id |
+------------+--------------+
|          1 |            5 |
|          2 |            1 |
|          3 |            3 |
|          4 |            2 |
|          5 |            4 |
+------------+--------------+
5 rows in set (0.00 sec)

mysql> select * from plantilla_detalle_horario;
+--------------+-----+--------------------+--------+
| plantilla_id | dia | codigo_incapacidad | turno  |
+--------------+-----+--------------------+--------+
|            1 |   1 | NULL               | 1/10   |
|            1 |   2 | NULL               | 1/11,5 |
|            1 |   3 | NULL               | 1/10   |
|            1 |   4 | NULL               | 1/11,5 |
|            1 |   5 | NULL               | 1/10   |
|            1 |   6 | vacaciones         | NULL   |
|            1 |   7 | vacaciones         | NULL   |
|            2 |   1 | NULL               | 2/11,5 |
|            2 |   2 | NULL               | 1/11,5 |
|            2 |   3 | NULL               | 2/11,5 |
|            2 |   4 | NULL               | 1|11.5 |
|            2 |   5 | NULL               | 1/11,5 |
|            2 |   6 | vacaciones         | NULL   |
|            2 |   7 | vacaciones         | NULL   |
|            3 |   1 | NULL               | 1#8    |
|            3 |   2 | NULL               | 1.0    |
|            3 |   3 | viaje_negocios     | NULL   |
+--------------+-----+--------------------+--------+
17 rows in set (0.00 sec)

mysql> select * from horario;
+------------+--------------+
| horario_id | plantilla_id |
+------------+--------------+
|          1 |            5 |
|          2 |            1 |
|          3 |            3 |
|          4 |            2 |
|          5 |            4 |
+------------+--------------+
5 rows in set (0.00 sec)

mysql> desc detalle_horario;
+--------------------+-------------+------+-----+---------+-------+
| Field              | Type        | Null | Key | Default | Extra |
+--------------------+-------------+------+-----+---------+-------+
| horario_id         | int         | NO   | PRI | NULL    |       |
| hora_salida        | date        | NO   | PRI | NULL    |       |
| hora_entrada       | date        | NO   |     | NULL    |       |
| codigo_incapacidad | varchar(25) | YES  |     | NULL    |       |
+--------------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> CREATE TABLE usuarios (
    ->     idx int(20) NOT NULL,
    ->     nombre varchar(100) NOT NULL,
    ->     apellidos varchar(100) NOT NULL,
    ->     departamento varchar(100) NOY NULL,
    ->     PRIMARY KEY (nombre, apellidos)
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'NOY NULL,
    PRIMARY KEY (nombre, apellidos)
)' at line 5
mysql> CREATE TABLE usuarios (
    ->     idx int(20) NOT NULL,
    ->     nombre varchar(100) NOT NULL,
    ->     apellidos varchar(100) NOT NULL,
    ->     departamento varchar(100) NOT NULL,
    ->     PRIMARY KEY (nombre, apellidos)
    -> ); 
Query OK, 0 rows affected, 1 warning (0.03 sec)

mysql> insert into detalle_horario (horario_id,hora_entrada,hora_salida,codigo_incapacidad) values (1,'2025/03/01 03:00' '2025/03/01 04:00', 'vaciones');
ERROR 1136 (21S01): Column count doesn't match value count at row 1
mysql> insert into detalle_horario (horario_id,hora_entrada,hora_salida,codigo_incapacidad) 
    -> values (1,'2025/03/01 10:00' '2025/03/01 06:00', 'vacaciones');
ERROR 1136 (21S01): Column count doesn't match value count at row 1
mysql> SELECT * from detalle_horario;
Empty set (0.01 sec)

mysql> INSERT into ,hora_salida,codigo_incapacidad) 
    -> values (1,'2025/03/01 11:10','2025/03/01 12:43', 'vacaciones');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ',hora_salida,codigo_incapacidad) 
values (1,'2025/03/01 11:10','2025/03/01 12:43' at line 1
mysql>  insert into detalle_horario (horario_id,hora_entrada,hora_salida,codigo_incapacidad)
    ->  values (12,'2025/03/01 03:00','2025/03/01 04:00','vaciones');
Query OK, 1 row affected, 4 warnings (0.00 sec)

mysql>  insert into detalle_horario (horario_id,hora_entrada,hora_salida,codigo_incapacidad)
    ->  values (13,'2025/04/02 04:00','2025/04/02 05:00','vaciones');
Query OK, 1 row affected, 4 warnings (0.00 sec)

mysql> insert into detalle_horario (horario_id,hora_entrada,hora_salida,codigo_incapacidad)
    ->  values (14,'2025/05/03 05:00','2025/05/03 06:00','vaciones');
Query OK, 1 row affected, 4 warnings (0.01 sec)

mysql> insert into detalle_horario (horario_id,hora_entrada,hora_salida,codigo_incapacidad)
    ->  values (15,'2025/06/04 06:00','2025/06/04 07:00','vaciones');
Query OK, 1 row affected, 4 warnings (0.00 sec)

mysql> insert into detalle_horario (horario_id,hora_entrada,hora_salida,codigo_incapacidad)
    ->  values (16,'2025/07/05 07:00','2025/07/05 08:00','vaciones');
Query OK, 1 row affected, 4 warnings (0.00 sec)

mysql> SELECT * from detalle_horario;
+------------+-------------+--------------+--------------------+
| horario_id | hora_salida | hora_entrada | codigo_incapacidad |
+------------+-------------+--------------+--------------------+
|         12 | 2025-03-01  | 2025-03-01   | vaciones           |
|         13 | 2025-04-02  | 2025-04-02   | vaciones           |
|         14 | 2025-05-03  | 2025-05-03   | vaciones           |
|         15 | 2025-06-04  | 2025-06-04   | vaciones           |
|         16 | 2025-07-05  | 2025-07-05   | vaciones           |
+------------+-------------+--------------+--------------------+
5 rows in set (0.00 sec)

mysql> INSERT into usuarios (idx; nombre, apellido, departamento) values ( 2, 'Karen', 'Hernandez', 'cbtis-246');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'nombre, apellido, departamento) values ( 2, 'Karen', 'Hernandez', 'cbtis-246')' at line 1
mysql> INSERT into usuarios (idx, nombre, apellido, departamento) values ( 2, 'Karen', 'Hernandez', 'cbtis-246');
ERROR 1054 (42S22): Unknown column 'apellido' in 'field list'
mysql> INSERT into usuarios (idx, nombre, apellido, departamento) values ( 2, 'Karen', 'paz', 'cbtis-246');
ERROR 1054 (42S22): Unknown column 'apellido' in 'field list'
mysql> INSERT into usuarios (idx, nombre, apellido, departamento) values (8,'Karen','paz','cbtis-246');
ERROR 1054 (42S22): Unknown column 'apellido' in 'field list'
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (8,'Karen','paz','cbtis-246');
Query OK, 1 row affected (0.01 sec)

mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (9,'Diana','Sanchez','cbtis-246');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (10,'Ximena','Saldaña','cbtis-246');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (12,'Alexa','Guerra','cbtis-246');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (19,'Luz','Flores','cbtis-246');
Query OK, 1 row affected (0.01 sec)

mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (16,'Emiliano','Alvarez','cbtis-246');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (15,'Jesus','Calderon','cbtis-246');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (17,'Leonardo','Chavez','cbtis-246');
Query OK, 1 row affected (0.01 sec)

mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (13'Karol','Ortiz','cbtis-246');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''Karol','Ortiz','cbtis-246')' at line 1
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (14'Abigail','Vasquez','cbtis-246');
INSERT into usuarios (idx, nombre, apellidos, departamento) values (14'Abigail','Vasquez','cbtis-246');
^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (18'Alondra','Garcia','cbtis-246');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''Alondra','Garcia','cbtis-246')' at line 1
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (14'Abigail','Vasquez','cbtis-246');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''Abigail','Vasquez','cbtis-246')' at line 1
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (14'Abigail','Vasquez','cbtis-246');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''Abigail','Vasquez','cbtis-246')' at line 1
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (14'Abigail','Vasquez','cbtis-246');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''Abigail','Vasquez','cbtis-246')' at line 1
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (14','Abigail','Vasquez','cbtis-246');
    '> ^C^C^Cc
c
^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (11','Alondra','Fernandez','cbtis-246');
    '> 
    '> c
    '> ^C^C^C^C^C^C^C^C^C^C^C^C^C^C

^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (11','Alondra','Fernandez','cbtis-246');
    '> 
    '> ^C^C^C^C^C^C^C^C^C

^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (11','Alondra','Fernandez','cbtis-246');
    '> INSERT into usuarios (idx, nombre, apellidos, departamento) values (11','Alondra','Fernandez','cbtis-246');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '','Alondra','Fernandez','cbtis-246');
INSERT into usuarios (idx, nombre, apellid' at line 1
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (29','Emilia','Zapata','cbtis-246');
    '> ^C^C^C^C^C^C^C^C^C

^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (29','Emilia','Zapata','cbtis-246');
    '> ^C^C^Ccc
cc
^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (29','Emilia','Zapata','cbtis-246');
    '> 
    '> 
    '> 
    '> 
    '> 
    '> ^C^C^C^C^C^C^C^C^C^C^C^C

^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (29','Emilia','Zapata','cbtis-246');
    '> ^Ccccc
cccc
^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (28','Emiliana','Zapata','cbtis-246);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '','Emiliana','Zapata','cbtis-246)' at line 1
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) vakues (20','Julieta','Suarez','cbtis-246);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'vakues (20','Julieta','Suarez','cbtis-246)' at line 1
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (59','Camila','Ramos','cbtis-246');
    '> ^C^C^C^C^C^C

^C
mysql> mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (9,'Diana','Sanchez','cbtis-246');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (9,'Di' at line 1
mysql> Query OK, 1 row affected (0.00 sec)
    -> ^C^C^C^C^C^C

^C
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (18,'Fernanda','Delgado','cbtis-246');
Query OK, 1 row affected (0.00 sec)
    '> 
mysql> SELECT * from usuarios;
+-----+----------+-----------+--------------+
| idx | nombre   | apellidos | departamento |
+-----+----------+-----------+--------------+
|  12 | Alexa    | Guerra    | cbtis-246    |
|   9 | Diana    | Sanchez   | cbtis-246    |
|  16 | Emiliano | Alvarez   | cbtis-246    |
|  18 | Fernanda | Delgado   | cbtis-246    |
|  15 | Jesus    | Calderon  | cbtis-246    |
|   8 | Karen    | paz       | cbtis-246    |
|  17 | Leonardo | Chavez    | cbtis-246    |
|  19 | Luz      | Flores    | cbtis-246    |
|  10 | Ximena   | Saldaña   | cbtis-246    |
+-----+----------+-----------+--------------+
9 rows in set (0.00 sec)
mysql> INSERT into usuarios (idx, nombre, apellidos, departamento) values (24,'Cristian','Jimenez','cbtis-246');
Query OK, 1 row affected (0.01 sec)
mysql> SELECT * from usuarios;
+-----+----------+-----------+--------------+
| idx | nombre   | apellidos | departamento |
+-----+----------+-----------+--------------+
|  12 | Alexa    | Guerra    | cbtis-246    |
|  24 | Cristian | Jimenez   | cbtis-246    |
|   9 | Diana    | Sanchez   | cbtis-246    |
|  16 | Emiliano | Alvarez   | cbtis-246    |
|  18 | Fernanda | Delgado   | cbtis-246    |
|  15 | Jesus    | Calderon  | cbtis-246    |
|   8 | Karen    | paz       | cbtis-246    |
|  17 | Leonardo | Chavez    | cbtis-246    |
|  19 | Luz      | Flores    | cbtis-246    |
|  10 | Ximena   | Saldaña   | cbtis-246    |
+-----+----------+-----------+--------------+
10 rows in set (0.00 sec)
mysql> h
