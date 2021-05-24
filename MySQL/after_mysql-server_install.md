# After MySQL Installation Things


[Guide](https://www.sqlshack.com/how-to-install-mysql-on-ubuntu-18-04/)

`mysql -V` or `mysql --version` to check version or if MySQL is installed on system

<b>Connect to MySQL instance</b>

```
vagrant@vagrant:~$ sudo mysql -u root -p                                                                                                  Enter password:                                                                                                                           Welcome to the MySQL monitor.  Commands end with ; or \g.                                                                                 Your MySQL connection id is 10                                                                                                            Server version: 8.0.23 MySQL Community Server - GPL                                                                                                                                                                                                                                 Copyright (c) 2000, 2021, Oracle and/or its affiliates.                                                                                                                                                                                                                             Oracle is a registered trademark of Oracle Corporation and/or its                                                                         affiliates. Other names may be trademarks of their respective                                                                             owners.                                                                                                                                                                                                                                                                             Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.                                                                                                                                                                                                      mysql> 
```
<b>Checking if server is running</b>

`systemctl status mysql.service`

<b>Uninstalling MySQL Server</b>

1. `sudo service mysql stop`
2. `sudo apt-get purge mysql-server mysql-client`
3. OK
4. `sudo apt-get autoremove`
5. `sudo apt-get autoclean`