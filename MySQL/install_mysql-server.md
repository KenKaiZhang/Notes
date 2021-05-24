# Installing MySQL 8.0.19 on Ubuntu 

[Guide](https://www.sqlshack.com/how-to-install-mysql-on-ubuntu-18-04/)

- Must run on Ubuntu 18.04 machine

<b>Download the latest MySQL APT Repository</b>

`wget -c https://dev.mysql.com/get/mysql-apt-config_0.8.15-1_all.deb`

<b>Install MySQL package</b>

`sudo dpkg -i mysql-apt-config_x.x.xx-x_all.deb`

<b>Select options:</b>
1. MySQL Server & Cluster -> OK
2. mysql-8.0 -> OK
3. OK

<b>Update and upgrade latest package information</b>

`sudo apt-get update && sudo apt-get upgrade -y`

<b>Install MySQL 8</b>

`sudo apt-get install mysql-server`

1. Enter a password -> OK
2. Use Strong Password Encryption -> OK 






