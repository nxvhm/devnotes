---
title: "Postgresql: Create New User/Database"
date: 2025-05-24T18:32:07+01:00
draft: false
tags: ['postgresql', 'sql', 'db', 'database']
---

Login as postgresql root user:
```sh
 sudo -u postgres psql
 ```
If you dont want to use root, use:
```
psql -U username -d dbname -h your_host
```

Create New user:
```sh
CREATE USER your_new_username WITH ENCRYPTED PASSWORD 'your_password';
```

Create Database:
```sh
CREATE DATABASE your_new_database;
```

Grant privileges
```sh
GRANT ALL PRIVILEGES ON DATABASE your_new_database TO your_new_username;
```

To check if user is created:
```sh
SELECT * FROM pg_user;
```

Detailed explanations on users:
https://www.strongdm.com/blog/postgres-create-user