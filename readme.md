# MySQL
![](https://kinsta.com/wp-content/uploads/2022/03/MySQL-logo-2048x1365.png)
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


