# SOURCE

running commands through prewritten files

``` terminal:
mysql> SOURCE /home/vagrant/mysql_scripts/count_users.sql
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
+----------+
| COUNT(*) |
+----------+
|        4 |
+----------+
1 row in set (0.02 sec)
```

- must provide full pathname or where the file exists if file is not in current directory
