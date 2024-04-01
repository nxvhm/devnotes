---
title: "Run Script in background on system startup with nohup"
date: 2022-05-06T22:34:23+03:00
tags: ["php", "linux"]
---

Install nohup which is used to run processes in background

```sh
sudo apt install nohup	
```

Create a simple shell script in `/usr/local/bin` which is gonna be responsible for starting the script via nohup.

```sh
#! /bin/sh
nohup php8.0 /path/to/myscript.php >/dev/null 2>&1 &
```

Make it executable:

```sh
sudo chmod u+x myscript.sh	
```

Symlink script to `/etc/init.d/`

```sh
sudo ln -s /usr/local/bin/myscript.sh /etc/init.d/
```

Symlink the symlink to /etc/rc2.d. Prepend the scriptname with S[NUMBER]. Number is used by the system to determine the order of executing the scripts in the /etc/rc2.d directory . We want our script last.

```sh
sudo ln -s /etc/init.d/myscript.sh /etc/rc2.d/S90myscript.sh
```
