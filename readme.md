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
HERE, `*.*` denotes database.table,this is used in order to give privileges to specific database or to a specific table of an database.

## REVOKE PRIVILEGES TO THE MYSQL NEW USER

* To Revoke all privileges   

   ```mysql> REVOKE ALL PRIVILEGES ON * . * TO peter@localhost; ```    

* To Revoke specific privileges  

   ```mysql> REVOKE CREATE, SELECT, INSERT ON * . * TO peter@localhost; ```   
  
> ***NOTE:***  
HERE, `*.*` denotes database.table,this is used in order to give privileges to specific database or to a specific table of an database.

## TYPES OF PRIVILEGES
1. Database privileges
2. Table privileges
3. Column privileges  
4. Stored routine privileges (yet to study)   

1. **DATABASE PRIVILEGES**  
   ***SYNTAX***  
   
   ```mysql> GRANT ALL PRIVILEGES ON database_name . * TO peter@localhost;```  
   
2. **TABLE PRIVILEGES**
   ***SYNTAX***  
   
   ```mysql> GRANT ALL PRIVILEGES ON database_name . table_name TO peter@localhost;```  
   
3. **COLUMN PRIVILEGES**
   ***SYNTAX***   
   
   ```mysql> GRANT INSERT(column_name),UPDATE(column_name) ON database_name . table_name TO peter@localhost;```  
   
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

* MySQL allows us to change the user account password in three different ways, which are given below:
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


