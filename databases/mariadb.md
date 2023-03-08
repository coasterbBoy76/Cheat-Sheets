# MariaDB Cheat-Sheet

## Install MariaDB on Ubuntu 20.04 LTS
```bash
sudo apt update
sudo apt install mariadb-server
sudo mysql_secure_installation
```

## Access Database from outside
Open `/etc/mysql/mariadb.conf.d/50-server.cnf` and change the `bind-address` to:
```
...

bind-address = 0.0.0.0

...
```
## Create Administrative User
1. Create a new user `newuser` for the host `localhost` with a new `password`:
```mysql
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
```

2. Grant all permissions to the new user
```mysql
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
``` 

3. Update permissions
```mysql
FLUSH PRIVILEGES;
```

## Update MariaDB User Password
1. Log in using Root account
```
mysql -u root -p
```

2. Switch to mysql databsae
```
MariaDB [(none)]> use mysql;
```

3. Update user password
```
MariaDB [mysql]> ALTER USER 'user'@'localhost' IDENTIFIED BY 'new_password';
```

4. Flush Permissions
```
MariaDB [mysql]> FLUSH PRIVILEGES;
```





## Adjusting Max Connections for Maria DB

To Adjust the Max Connections.
1. Log into Maria Db using Root

The following command will the current default max connections.
```
show variables like "max_connections";
```

2. Increase Max Connections.
The following command will increase the MAZ connections without a restart. Once the server has been restarted the value will reset.
```
set global max_connections = 200;
```


2A. To permanetly increase max connections, open <i>my.cnf</i> file
```
$ sudo vim /etc/my.cnf
```

Add the followinf line under [mysqld]
```
max_connections = 200
```

Restart Maria DB service
```
sudo service myslq restart
```
