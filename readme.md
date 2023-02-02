# MySQL
![MySQL](https://kinsta.com/wp-content/uploads/2022/03/MySQL-logo-2048x1365.png)
## About
[**Check Here**](https://kinsta.com/blog/postgresql-vs-mysql/#:~:text=MySQL%20is%20a%20purely%20relational,%2C%20ACID%2Dcompliant%20storage%20engine.)
## MySQL VS PostgreSQL

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

# USER MANAGEMENT
## CREATE USER

   ***SYNTAX***     

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
   
   ***SYNTAX***  
   
   ```mysql> GRANT ALL PRIVILEGES ON database_name.* TO dileep@localhost;```  
2. **TABLE PRIVILEGES**  

   ***SYNTAX***  
   
   ```mysql> GRANT ALL PRIVILEGES ON database_name.table_name TO dileep@localhost;```  
3. **COLUMN PRIVILEGES**  

   ***SYNTAX***   
   
   ```mysql> GRANT INSERT(column_name),UPDATE(column_name) ON database_name.table_name TO dileep@localhost;```  
4. **STORED ROUTINES**
* It applies to stored routines (procedure and functions). It contains CREATE ROUTINE, ALTER ROUTINE, EXECUTE, and GRANT OPTION 
  privileges. Here, a user can execute the stored procedure in the current database.  

   ***SYNTAX***   
   
   ```mysql> GRANT EXECUTE ON PROCEDURE|FUNCTION database_name.procedure_name|function_name TO dileep@localhost;```
5. **PROXY**
* It enables one user to be a proxy for other users. 

   ***SYNTAX***   
   
   ```mysql> GRANT PROXY ON root TO dileep@localhost;```  
## REVOKE PRIVILEGES
* MySQL provides REVOKE statements to remove privileges from a user account.  

1. **REMOVE GLOBAL PRIVILIGES AND GRANT OPTION**
***SYNTAX***  

```mysql> REVOKE ALL,GRANT OPTION ON *.* FROM dileep@localhost; ```  
2. **REMOVE ALL OTHER PRIVILEGES TYPES**
* We can remove all other privileges from user by replacing "GRANT" with "REVOKE" and since we are taking back privileges from users.   so, we can replace "TO" with "FROM"

## DROP USER

   ***SYNTAX***   

   ```mysql> DROP USER 'account_name';  ```

## SHOW USERS

   ***SYNTAX***   

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

   ***SYNTAX*** 

   ```mysql> UPDATE user SET authentication_string = PASSWORD('jtp12345') WHERE user = 'peter' AND host = 'localhost';```
2. **SET PASSWORD Statement**  

   ***SYNTAX***  

   ```mysql> SET PASSWORD FOR 'peter'@'localhost' ='jtp12345';```  
3. **ALTER USER Statement**  

   ***SYNTAX***    

   ```mysql> ALTER USER peter@localhost IDENTIFIED BY 'jtp123';```  
>***NOTE:***  
   It's better to use second and third ways,as the password we are saving is encrypted and can't access it using authentication_string from mysql database.

## GRANT OPTION

* Grant option is used to give privileges to an user,which allows user to give privileges to it's users,without the need of user's host.
* we can give this grant option at the creation of user.  
 
   ***SYNTAX***    

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

# DATABASE

## CREATE DATABASE  
   ***SYNTAX***  

   ```mysql> CREATE DATABASE [IF NOT EXISTS] database_name [CHARACTER SET charset_name] [COLLATE collation_name]; ```  

## SELECT DATABASE  
   ***SYNTAX***  

   ```mysql> USE [IF EXISTS] database_name ; ```  
## SHOW DATABASES
   ***SYNTAX***  

   ```mysql> SHOW DATABASES; ```  

* Show Databases Using Pattern Matching  
 
   ```mysql> SHOW DATABASES LIKE pattern; ```  

## DROP DATABASES  
   ***SYNTAX***

   ```mysql> DROP DATABASE|SCHEMA [IF EXISTS] database_name; ```  
## COPY DATABASE
1. Use the CREATE DATABASE statement to create a new database.  

   ***SYNTAX***  

   ```mysql> CREATE DATABASE database_name; ``` 
2. open a DOS or terminal window to access the MySQL server on the command line. Store the data to an SQL file. We can give any name to 
   this file, but it must end with a .sql extension. Export all the database objects along with its data to copy using the mysqldump 
   tool.  

   ***SYNTAX***  

   ```mysqldump -u root -p database_name > path; ```  
3. Then,import this file into the new database.  

   ***SYNTAX***  
   
   ```mysqldump -u root -p new_database_name < path; ```  
# TABLES

## CREATE TABLE









