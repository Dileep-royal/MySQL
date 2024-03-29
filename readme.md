# MySQL
![MySQL](https://kinsta.com/wp-content/uploads/2022/03/MySQL-logo-2048x1365.png)   

![30 Days of SQl](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210205194115/30-Days-of-SQL-%E2%80%93-From-Basic-to-Advanced-Level.png) 

## About
[**Check Here**](https://kinsta.com/blog/postgresql-vs-mysql/#:~:text=MySQL%20is%20a%20purely%20relational,%2C%20ACID%2Dcompliant%20storage%20engine.)
## MySQL VS PostgreSQL
* MySQL & postgreSQL are the two best and popular databases.
* Here,below are the differences between them ,which help you to choose best fit for you.  

| MySQL                                                                                                	| PostgreSQL                                                                                                                                                	|
|------------------------------------------------------------------------------------------------------	|-----------------------------------------------------------------------------------------------------------------------------------------------------------	|
| Popular Database                                                                                     	| Advanced & Modern Database                                                                                                                                	|
| It was developed in 1995 by a Swedish company named MySQL AB.                                        	| It was developed in 1986 under the direction of Professor "Michael Stonebreaker" at the University of California, Berkeley.                               	|
| Realational based DBMS (RDBMS)                                                                       	| object & relational based DBMS (ORDBMS)                                                                                                                   	|
| It is an ACID-compliant only when used with InnoDB and NDB cluster engines                           	| It is an ACID-compliant from the ground up.                                                                                                               	|
| MySQL offers support for 15 different storage engines apart from its default storage engine, InnoDB. 	| PostgreSQL houses a single, ACID-compliant storage engine.                                                                                                	|
| MySQL isn’t as fully SQL-compliant                                                                   	| It is fully SQL-compliant as it supports several subqueries, like "LIMIT" or "ALL" & standard SQL clauses like "INTERSECT" or "OUTER JOIN".               	|
|                                                                                                      	| In contrast, PostgreSQL is more SQL-compliant than MySQL, supporting most of the primary SQL features — 160 out of 179 mandatory features, to be precise. 	|
| The implementation language is C/C++.                                                                	| The implementation language is C.                                                                                                                         	|
| GUI tool provided is MySQL Workbench.                                                                	| GUI tool provided is PgAdmin.                                                                                                                             	|
| It does not support partial, bitmap, and expression indexes.                                         	| It supports all types of indexes.                                                                                                                         	|
| It doesn’t provide support for Materialised views and Table inheritance.                             	| PostgreSQL provides both of them.                                                                                                                         	|
| SQL only supports Standard data types.                                                               	| It supports Advanced data types such as arrays, hstore, and user-defined types.                                                                           	|
| SQL provides limited MVCC support (in InnoDB Engine)                                                 	| Full MVCC(Multi-Version Concurrency Control) support, Achieved through Snapshot isolation, which helps to overcome read-write lock.                       	|
| It is reliable, simple, and faster.                                                                  	| It is slower and more complex.                                                                                                                            	|
| MySQL is generally known to be faster with read-only commands at the cost of concurrency             	| PostgreSQL works better with read-write operations, massive datasets, and complicated queries.                                                            	|
| Troubleshooting MySQL is easy.                                                                       	| It is difficult to troubleshoot PostgreSQL.                                                                                                               	|
| Cloud-ready DBMS                                                                                     	| Not a Cloud-ready DBMS                                                                                                                                    	|
| Every Connection created is an OS Thread.                                                            	| Every Connection created is an OS Process, means requires lot of memory on systems.                                                                       	|
| Manages Maximum of 8 Tera Bytes of data,50M rows.                                                    	| Manages maximum of 4 Peta Bytes of data.      |

## SQL COMMANDS

The SQL commands are categorized into the following categories:  

DDL - Data Definition Language  

DML - Data Manipulation Language  

DQL - Data Query Language  

DCL - Data Control Language  

TCL - Transaction Control Language   

1. **DDL**
* Queries like-CREATE,DROP,TRUNCATE,and ALTER fall into this category because they all manage the structure of DB Objects in some way.  
>Eg: CREATE command creates the structure of a table, DROP command removes the table structure.
2. **DML**
* Queries like DELETE, UPDATE and INSERT fall into this category because they all manipulate the data in some way.
>Eg: the DELETE command removes data in a table, UPDATE command updates the data.
3. **DQL**
* The SELECT query falls into this category because it is used to query the database and get the output of the query.
>Eg: Using SELECT, we can ask any specific question to a DB and get answers.
4. **DCL**
* Queries like GRANT, and REVOKE fall into this category because they're used to control access to the DB.
>Eg: GRANT will assign permission to a user on a DB Object and REVOKE will remove the permission.  
5. **TCL**
* Queries like ROLLBACK, COMMIT & SAVE POINT fall into this category as they're used to manage transactions in the database.
>Eg: the COMMIT command commits the transaction and the ROLLBACK command rollback all changes done to a DB when a transaction fails.

## CONSTRAINTS
* The constraint in MySQL is used to specify the rule that allows or restricts what values/data will be stored in the table.
* Used to ensure data accuracy and integrity inside the table. 

Constraints in MySQL is classified into two types:
1. **Column Level Constraints:**
   These constraints are applied only to the single column that limits the type of particular column data.
2. **Table Level Constraints:**
   These constraints are applied to the entire table that limits the type of data for the whole table.
The following are the most common constraints used in the MySQL:  

   1. NOT NULL
      * This constraint specifies that the column cannot have NULL or empty values.
      >Eg: ``` email varchar(30) NOT NULL ```
   2. CHECK
      * It ensures that the inserted value in a column must be satisfied with the given condition.
      > Syntax: ``` CHECK(expression) ```  

        Eg:``` age int CHECK(age>=18) ```    
   3. DEFAULT
      * This constraint is used to set the default value for the particular column where we have not specified any value.
      >Eg: ``` city varchar(30) DEFAULT 'new york' ```
   4. PRIMARY KEY
      * This constraint is used to identify each record in a table uniquely. If the column contains primary key constraints, then it cannot be null or empty.
      >Eg: ``` id INT PRIMARY KEY AUTO_INCREMENT ```
   5. AUTO_INCREMENT
      * This constraint automatically generates a unique number whenever we insert a new record into the table. Generally, we use this constraint for the primary key field in a table.
      >Eg: ``` id INT PRIMARY KEY AUTO_INCREMENT ```
   6. UNIQUE
      * This constraint ensures that all values inserted into the column will be unique.
      >Eg: ``` email varchar(30) UNIQUE ```
   7. INDEX
      * This constraint allows us to create and retrieve values from the table very quickly and easily. An index can be created using one or more than one column. It assigns a ROWID for each row in that way they were inserted into the table.
      >Eg: ``` CREATE INDEX idx_name ON Shirts(name); ```
   8. ENUM
      * The ENUM data type in MySQL is a string object. It allows us to limit the value chosen from a list of permitted values in the column specification at the time of table creation. 
      >Eg: ```size ENUM('small', 'medium', 'large', 'x-large')```
   9. FOREIGN KEY
      * This constraint is used to link two tables together. It is also known as the referencing key. A foreign key column matches the primary key field of another table. It means a foreign key field in one table refers to the primary key field of another table.
      >Eg: ``` Person_ID INT FOREIGN KEY REFERENCES Persons(id) ``` 

# USER MANAGEMENT
## CREATE USER

   **SYNTAX**     

   ```mysql> CREATE USER [IF NOT EXISTS] account_name IDENTIFIED BY 'password';```  

   In the above syntax, the account_name has two parts one is the username, and another is the hostname, which is separated by @ symbol. Here, the username is the name of the user, and the hostname is the name of the host from which the user can connect with the database server.

## GRANT PRIVILEGES TO THE MYSQL NEW USER

   * To Grant all privileges   

      ```mysql> GRANT ALL PRIVILEGES ON * . * TO peter@localhost; ```   

   * To grant specific privileges   

      ```mysql> GRANT CREATE, SELECT, INSERT ON * . * TO peter@localhost; ``` 
   * To flush all the privileges of a user account for changes occurs immediately  

      ```mysql> FlUSH PRIVILEGES ```
   * To see existing privileges of an user  

      ```mysql> SHOW GRANTS for username;```   
      
   > ***NOTE:***  
      Here, `*.*` denotes database.table,this is used in order to give privileges to specific database or to a specific table of an database.

## REVOKE PRIVILEGES TO THE MYSQL NEW USER

   * To Revoke all privileges   

      ```mysql> REVOKE ALL PRIVILEGES ON * . * TO peter@localhost; ```    

   * To Revoke specific privileges  

      ```mysql> REVOKE CREATE, SELECT, INSERT ON * . * TO peter@localhost; ```   
   
   > ***NOTE:***  
      Here, `*.*` denotes database.table,this is used in order to give privileges to specific database or to a specific table of an database.
## GRANT PRIRVILEGES
   ### TYPES OF PRIVILEGES
   1. Database privileges
   2. Table privileges
   3. Column privileges  
   4. Stored routine privileges   
   5. Proxy  

   The types of privileges are explained below:  

   1. **DATABASE PRIVILEGES**  
      
      **SYNTAX**  
      
      ```mysql> GRANT ALL PRIVILEGES ON database_name.* TO dileep@localhost;```  
   2. **TABLE PRIVILEGES**  

      **SYNTAX**  
      
      ```mysql> GRANT ALL PRIVILEGES ON database_name.table_name TO dileep@localhost;```  
   3. **COLUMN PRIVILEGES**  

      **SYNTAX**   
      
      ```mysql> GRANT INSERT(column_name),UPDATE(column_name) ON database_name.table_name TO dileep@localhost;```  
   4. **STORED ROUTINES**
   * It applies to stored routines (procedure and functions). It contains CREATE ROUTINE, ALTER ROUTINE, EXECUTE, and GRANT OPTION 
   privileges. Here, a user can execute the stored procedure in the current database.  

      **SYNTAX**   
      
      ```mysql> GRANT EXECUTE ON PROCEDURE|FUNCTION database_name.procedure_name|function_name TO dileep@localhost;```
   5. **PROXY**
   * It enables one user to be a proxy for other users. 

      **SYNTAX**   
      
      ```mysql> GRANT PROXY ON root TO dileep@localhost;```  
## REVOKE PRIVILEGES
* MySQL provides REVOKE statements to remove privileges from a user account.  
1. **REMOVE GLOBAL PRIVILIGES AND GRANT OPTION**  
**SYNTAX**  

   ```mysql> REVOKE ALL,GRANT OPTION ON *.* FROM dileep@localhost; ```  
  
2. **REMOVE ALL OTHER PRIVILEGES TYPES**  

   We can remove all other privileges from user by replacing "GRANT" with "REVOKE" and since we are taking back privileges from users.so, we can replace "TO" with "FROM"

## DROP USER

   **SYNTAX**   

   ```mysql> DROP USER 'account_name';  ```

## SHOW USERS

   **SYNTAX**   

   ```mysql> SELECT user from mysql.user; ```

   * To get the selected information like as hostname, password expiration status, and account locking   

      ```mysql> SELECT user, host, account_locked, password_expired FROM user;```

   * TO show current user  

      ```mysql> SELECT current_user()/user(); ```

   * To see the currently logged user in the database server  

      ```mysql> SELECT user, host, db, command FROM information_schema.processlist; ```

## CHANGE MYSQL USER PASSWORD

*  MySQL allows us to change the user account password in three different ways, which are given below:
1. UPDATE Statement
2. SET PASSWORD Statement
3. ALTER USER Statement  
   
The Ways are Explained below:  

   1. **UPDATE Statement**  
      **SYNTAX** 

      ```mysql> UPDATE user SET authentication_string = PASSWORD('jtp12345') WHERE user = 'peter' AND host = 'localhost';```
   2. **SET PASSWORD Statement**  
      **SYNTAX**  

      ```mysql> SET PASSWORD FOR 'peter'@'localhost' ='jtp12345';```  
   3. **ALTER USER Statement**  
      **SYNTAX**    

      ```mysql> ALTER USER peter@localhost IDENTIFIED BY 'jtp123';```  
>***NOTE:***  
It's better to use second and third ways,as the password we are saving is encrypted and can't access it using authentication_string from mysql database.

## GRANT OPTION

   * Grant option is used to give privileges to an user,which allows user to give privileges to it's users,without the need of user's host. 
   * we can give this grant option at the creation of user.  
   
      **SYNTAX**    

      ```mysql> CREATE USER [IF NOT EXISTS] account_name IDENTIFIED BY 'password' WITH GRANT OPTION; ```

## ALTER USER
 
*The ALTER USER statement modifies MySQL accounts. It enables authentication, role, SSL/TLS, resource-limit, password-management, comment, and attribute properties to be modified for existing accounts. It can also be used to lock and unlock accounts.  

*In most cases, ALTER USER requires the global CREATE USER privilege, or the UPDATE privilege for the mysql system schema  

[**kNOW MORE ABOUT HERE**](https://dev.mysql.com/doc/refman/8.0/en/alter-user.html)

## PASSWORD MANAGEMENT

* Password expiration, to require passwords to be changed periodically.  

* Password reuse restrictions, to prevent old passwords from being chosen again.  

* Password verification, to require that password changes also specify the current password to be replaced.  

* Dual passwords, to enable clients to connect using either a primary or secondary password.  

* Password strength assessment, to require strong passwords.  

* Random password generation, as an alternative to requiring explicit administrator-specified literal passwords.  

* Password failure tracking, to enable temporary account locking after too many consecutive incorrect-password login failures.  

[**kNOW MORE ABOUT HERE**](https://dev.mysql.com/doc/refman/8.0/en/password-management.html)  

## LOCKING AND UNLOCKING ACCOUNT
1. **Locking the Account of new user**  
   **SYNTAX**  

   ```mysql> CREATE USER 'dileep'@'localhost' identified by 'password' ACCOUNT LOCK; ```
2. **Locking the account of existing user**  
   **SYNTAX**  

   ```mysql> ALTER USER 'dileep'@'localhost' identified by 'password' LOCK ACCOUNT; ```  
3. **To check user account is locked**  
   **SYNTAX**  

   ```mysql> SELECT user,host,account_locked FROM mysql.user; ```  
4. **To show the number of attempts to connect to the MySQL Server of locked accounts**  
   **SYNTAX**   

   ```mysql>SHOW GLOBAL STATUS LIKE  'locked_connects'; ```

5. **Account Unlocking**  
   **SYNTAX**  

   ```mysql> UNLOCK ACCOUNT 'dileep'@'localhost'; ```  

# DATABASE

## CREATE DATABASE  
   **SYNTAX**  

   ```mysql> CREATE DATABASE [IF NOT EXISTS] database_name [CHARACTER SET charset_name] [COLLATE collation_name]; ```  

## SELECT DATABASE  
   **SYNTAX**  

   ```mysql> USE [IF EXISTS] database_name ; ```  
## SHOW DATABASES
   **SYNTAX**  

   ```mysql> SHOW DATABASES; ```  

* Show Databases Using Pattern Matching  
   
   ```mysql> SHOW DATABASES LIKE pattern; ```  

## DROP DATABASES  
   **SYNTAX**

   ```mysql> DROP DATABASE|SCHEMA [IF EXISTS] database_name; ```  
## COPY DATABASE
1. Use the CREATE DATABASE statement to create a new database.  

   **SYNTAX**  

   ```mysql> CREATE DATABASE database_name; ``` 
2. open a DOS or terminal window to access the MySQL server on the command line. Store the data to an SQL file. We can give any name to this file, but it must end with a .sql extension. Export all the database objects along with its data to copy using the mysqldump tool.  

   **SYNTAX**  

   ```mysqldump -u root -p database_name > path; ```  
3. Then,import this file into the new database.  

   **SYNTAX**  

   ```mysqldump -u root -p new_database_name < path; ```  
# TABLES
## CREATE TABLE
   **SYNTAX**  

   ```mysql> CREATE TABLE [IF NOT EXISTS] table_name( column_definition1,column_definition2, ........,table_constraints); ``` 
## ALTER TABLE
1. **ADD COLUMN**  

   **SYNTAX**   

   ```mysql> ALTER TABLE [IF EXISTS] table_name ADD new_column_name column_defination FiRST|AFTER column_name; ```  
2. **MODIFY COLUMN**  

   **SYNTAX**    

   ```mysql> ALTER TABLE [IF EXISTS] table_name MODIFY column_name column_defination FIRST|AFTER column_name; ```
3. **DROP COLUMN**  

   **SYNTAX**  

   ```mysql> ALTER TABLE [IF EXISTS] table_name DROP COLUMN column_name; ```
4. **RENAME COLUMN**  

   **SYNTAX**  

   ```mysql> ALTER TABLE [IF EXISTS] table_name RENAME COLUMN old_column_name TO new_column_name column_defination FIRST|AFTER column_name; ```
5. **RENAME TABLE**  

   **SYNTAX**  

   ```mysql> ALTER TABLE [IF EXISTS] table_name RENAME TO new_table_name; ```  

## SHOW TABLES
   **SYNTAX**  

   ```mysql> SHOW TABLES; ```
   * Showing tables with pattern matching  

      ```mysql> SHOW TABLES LIKE pattern; ```
   * Showing tables from a particular tables  

      ```mysql> SHOW TABLES FROM|IN database_name; ```
## RENAME TABLE
   **SYNTAX**  

   ```mysql> RENAME old_table_name TO new_table_name; ```

   > ***NOTE:***
   The Above statement RENAME TABLE is used to change only normal table name,but it cannot work with temporary tables. In case of temporary tables use ALTER statement to do so.

   * From the MySQL 8.0.13 version, we can change the old table name locked with a LOCK statement and also uses the WRITE LOCK clause.  

     ```mysql> LOCK TABLE old_tab_name1 WRITE; ```  

     ```mysql> RENAME TABLE old_tab_name1 TO new_tab_name1,new_tab_name1 TO new_tab_name2; ```  
   * Where as old table name locked with READ clause is doesn't allow to Rename a table,it throws an error.  

     ```mysql> LOCK TABLE old_tab_name1 READ; ```   

     ```mysql> RENAME TABLE old_tab_name1 TO new_tab_name1,new_tab_name1 TO new_tab_name2; ```
   * MySQL also use the RENAME TABLE statement for moving a table from one database to other database.  

     ```mysql> RENAME TABLE current_database.table_name TO other_database.table_name; ```  
## TRUNCATE TABLE
   * We cannot rollback the deleted data after executing this command because the log is not maintained while performing this operation.
   * We cannot use the truncate statement when a table is referenced by a foreign key or participates in an indexed view.
      * In that case, we need to log into the MySQL server and disable foreign key checks before executing the TRUNCATE statement  

         ```mysql> SET FOREIGN_KEY_CHECKS=0; ```  
        Now,we can truncate the tables  
      * After execution, re-enable foreign key checks  

         ```mysql> SET FOREIGN_KEY_CHECKS=1; ```
   * The TRUNCATE command doesn't fire DELETE triggers associated with the table that is being truncated because it does not operate on individual rows.  
## DESCRIBE TABLE
   **SYNTAX**  

   ```mysql> DESCRIBE table_name; ```  
   
   ```mysql> SHOW COLUMNS FROM table_name; ``` 
   * If we want to display the more column information, we need to add FULL keyword with the SHOW TABLES statement  

     **SYNTAX**  

     ```mysql> SHOW FULL COLUMNS FROM table_name; ```
## DROP TABLE
   **SYNTAX**  

   ```mysql> DROP [TEMPORARY] TABLE [IF EXISTS] table_name; ```

## TEMPORARY TABLE
   ### CREATE TEMPORARY TABLE 
   **SYNTAX**  

   ```mysql> CREATE TEMPORARY TABLE [IF EXISTS] table_name (column1,column2,....,table_constraints); ```
 * If the user wants to create a temporary table whose structure is the same as an existing table in the database  

   ```mysql> CREATE TEMPORARY TABLE temporary_table_name SELECT * FROM original_table_name LIMIT 0; ```
## COPY TABLE
 * copying data along without its dependent objects  

   **SYNTAX**  

   ```mysql> CREATE TABLE new_table_name SELECT * FROM existing_table_name;  ```  
 * copying partial data   
   
   **SYNTAX**  

   ```mysql> CREATE TABLE new_table_name SELECT * FROM existing_table_name WHERE condition;  ```
 * copying data along with its dependent objects  
   
   **SYNTAX**  

   ```mysql> CREATE TABLE [IF NOT EXISTS] new_table_name LIKE existing_table_name;  ```  

   ```mysql> INSERT new_table_name SELECT * FROM existing_table_name; ```   

## UPDATE & DELETE(DML)
1. **UPDATE**
**SYNTAX**  

```mysql>UPDATE table_name SET column_name1=value1, colum_name2=value2,... WHERE condition; ```
2. **DELETE**
**SYNTAX**  

```mysql> DELETE FROM table_name WHERE condition; ```  

## TABLE LOCKING
   ### LOCK STATEMENT
   **SYNTAX**  

   ```mysql> LOCK TABLES table_name [READ | WRITE]; ```  
   **READ LOCK:** This lock allows a user to only read the data from a table.  

   **WRITE LOCK:** This lock allows a user to do both reading and writing into a table. 
   ### UNLOCK STATEMENT
   ```mysql> UNLOCK TABLE table_name; ```  
>***NOTE:***
   1. Read lock is similar to "shared" locks because multiple threads can acquire it at the same time.  
   2. Write lock is an "exclusive" locks because another thread cannot read it. 

# VIEWS

* The views are definitions built on top of other tables (or views).
* If any changes occur in the underlying table, the same changes reflected in the View also.  
* A view does not store the data physically. When we execute the SELECT statement for the view, MySQL uses the query specified in the view's definition and produces the output. Due to this feature, it is sometimes referred to as a virtual table.

**SYNTAX**  

```mysql> CREATE [OR REPLACE] VIEW view_name AS SELECT columns FROM tables [WHERE conditions]; ```

### CREATE VIEW
**SYNTAX**  

```mysql> CREATE VIEW view_name AS SELECT columns FROM tables [WHERE conditions]; ```
### UPDATE VIEW
**SYNTAX**  

```mysql> ALTER VIEW view_name AS SELECT columns FROM tables [WHERE conditions] ``` 

### DROP VIEW
**SYNTAX**  

```mysql> DROP VIEW view_name; ``` 

## INSERT IGNORE AND INSERT ON DUPLICATE KEY UPDATE
INSERT IGNORE and INSERT ON DUPLICATE KEY UPDATE statement avoids error in case of following Scenarios :
* When we will try to insert a duplicate key where the column of a table has a PRIMARY or UNIQUE KEY constraint.
* When we will try to add a NULL value where the column of a table has a NOT NULL constraint.
* When we will try to insert a record to a partitioned table where the entered values do not match the format of listed partitions. 

They are Explained below:  

1. **INSERT ON DUPLICATE KEY UPDATE**  

   This Statement update the specified column values,when duplicate key occurs.  

      **SYNTAX**  

      ```mysql> INSERT INTO table (column_names) VALUES (data) ON DUPLICATE KEY UPDATE column1 = expression, column2 = expression…;```
   >Eg:  It updates city column with 'california' ,because of the Stud_ID 4 alredy exists in table(duplicate key)
   ```mysql> INSERT INTO Student(Stud_ID, Name, Email, City) VALUES (4, 'John', 'john@gmail.com', 'New York') ON DUPLICATE KEY UPDATE City = 'California'; ```

2. **INSERT IGNORE**  

   This Statement simply allows us to handle errors smoothly in case of above scenarios.  

      **SYNTAX**  

      ```mysql> INSERT IGNORE INTO table_name (column_names) VALUES ( value_list), ( value_list) .....;  ```
   >Eg: If an Stud_ID is PRIMARY KEY and stud_ID "4" is already present in table,then simply it gives warning 
   ```mysql> INSERT IGNORE INTO Student(Stud_ID, Name, Email, City) VALUES (4,'Donald', 'donald@gmail.com', 'New York');  ```

## INDEXES
* An index is a data structure that allows us to add indexes in the existing table. 
* It enables you to improve the faster retrieval of records on a database table. 
* It creates an entry for each value of the indexed columns. 
* We use it to quickly find the record without searching each row in a database table whenever the table is accessed. 
* When a table is created with a primary key or unique key, it automatically creates a special index named PRIMARY. 
* We called this index as a clustered index. 
* All indexes other than PRIMARY indexes are known as a non-clustered index or secondary index.
### CREATE INDEX
**SYNTAX**

``` CREATE INDEX [index_name] ON [table_name] (column names); ```  
### SHOW INDEX
**SYNTAX**  

``` SHOW INDEXES FROM table_name; ```  
### DROP INDEX
**SYNTAX**   

``` DROP INDEX index_name ON table_name [algorithm_option][lock_option]; ```
### DROP PRIMARY KEY INDEX OF TABLE
**SYNTAX**  

``` DROP INDEX PRIMARY ON table_name ; ```

### CREATE UNIQUE KEY INDEX
**SYNTAX**   

```mysql> CREATE UNIQUE INDEX index_name ON table_name(column_names); ```
### CLUSTERED VS NON-CLUSTERED INDEX
To know - [Click Here](https://www.javatpoint.com/mysql-clustered-vs-non-clustered-index)

## MYSQL CLAUSES
### WHERE
* MySQL WHERE Clause is used with SELECT, INSERT, UPDATE and DELETE clause to filter the results. 
* It specifies a specific position where you have to do the operation.
**SYNTAX**  

```WHERE conditions; ```
### DISTINCT 
* MySQL DISTINCT clause is used to remove duplicate records from the table and fetch only the unique records. 
* The DISTINCT clause is only used with the SELECT statement. 
**SYNTAX**  

``` SELECT DISTINCT expressions FROM tables [WHERE conditions]; ```
### FROM 
* The MySQL FROM Clause is used to select some records from a table. 
* It can also be used to retrieve records from multiple tables using JOIN condition.
**SYNTAX**  

```  FROM table1 [ { INNER JOIN | LEFT [OUTER] JOIN| RIGHT [OUTER] JOIN } table2 ON table1.column1 = table2.column1 ] ```

### ORDER BY 
* The MYSQL ORDER BY Clause is used to sort the records in ascending or descending order.
**SYNTAX**  

```SELECT expressions FROM tables [WHERE conditions] ORDER BY expression [ ASC | DESC ];  ```
### GROUP BY 
* The MYSQL GROUP BY Clause is used to collect data from multiple records and group the result by one or more column. 
* It is generally used in a SELECT statement.
* It is also used with some aggregate functions like COUNT, SUM, MIN, MAX, AVG etc. on the grouped column.
**SYNTAX**  

``` SELECT expression1, expression2, ... expression_n,aggregate_function (expression) AS some_name FROM tables [WHERE conditions] GROUP BY expression1, expression2, ... expression_n;  ```
### HAVING 
* MySQL HAVING Clause is used with GROUP BY clause. It always returns the rows where condition is TRUE.
**SYNTAX**   

``` SELECT expression1, expression2, ... expression_n,aggregate_function (expression) AS some_name FROM tables [WHERE conditions] GROUP BY expression1, expression2, ... expression_n HAVING condition;  ```

## MYSQL KEYS
### UNIQUE KEY
### PRIMARY KEY
### FOREIGN KEY
### COMPOSITE KEY

## 












