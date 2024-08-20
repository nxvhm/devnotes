---
title: "MySQL: Create User and Database"
date: 2024-08-20T20:47:12+03:00
draft: false
tags: ['mysql', 'sql', 'db', 'database']
---

Login with mysql client

#### Create new user
```sh
CREATE USER 'new_user'@'localhost' IDENTIFIED BY 'password';
```

#### In order to grant all privileges of the database for a newly created user, execute the following command: 
```sh
GRANT ALL PRIVILEGES ON * . * TO 'new_user'@'localhost'; // grant on all
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
```
For changes to take effect immediately flush these privileges by typing in the command: 
```sh
FLUSH PRIVILEGES;
```

#### Revoke Privileges
```sh
REVOKE ALL PRIVILEGES ON * . * FROM 'user_name'@'localhost';
```

#### Delete User
```sh
DROP USER ‘user_name’@‘localhost’;
```

#### Show Privileges
```sh
SHOW GRANTS FOR 'user_name'@'localhost';
```

#### Create database
```sh
CREATE DATABASE IF NOT EXISTS new_database;
```