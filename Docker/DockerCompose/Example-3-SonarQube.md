root@e66d3de209f5:/# su - postgres
No directory, logging in with HOME=/
$
$
$ psql
psql (10.4 (Debian 10.4-2.pgdg90+1))
Type "help" for help.

postgres=# \list
                                 List of databases
   Name    |  Owner   | Encoding |  Collate   |   Ctype    |   Access privileges
-----------+----------+----------+------------+------------+-----------------------
 postgres  | postgres | UTF8     | en_US.utf8 | en_US.utf8 |
 sonar     | postgres | UTF8     | en_US.utf8 | en_US.utf8 |
 template0 | postgres | UTF8     | en_US.utf8 | en_US.utf8 | =c/postgres          +
           |          |          |            |            | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.utf8 | en_US.utf8 | =c/postgres          +
           |          |          |            |            | postgres=CTc/postgres
(4 rows)

postgres=# \connect sonar
You are now connected to database "sonar" as user "postgres".
sonar=# \dt
sonar=# \q
could not save history to file "/home/postgres/.psql_history": No such file or directory
$ exit
root@e66d3de209f5:/#
