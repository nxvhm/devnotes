---
title: "Postgresql: Whitelist IP"
date: 2025-04-10T20:47:12+03:00
draft: false
tags: ['postgresql', 'sql', 'db', 'database']
---

Edit `pg_hba.conf` file located in `/etc/postgresql/{version}/main/pg_hba.conf`.

Example entry to allow IP Address 10.20.30.40 to connect to `test` database
```
host    test     test             10.20.30.40/32            md5
```

Restart postgresql:
```sh
sudo service postgresql restart
```

Check if server is running and accepting connections:
```
pg_isready
```