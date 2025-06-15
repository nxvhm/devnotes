---
title: "Usefull Linux Commands"
date: 2024-03-06T22:34:23+03:00
tags: ['linux', 'php']
---

### Change default php cli version
```sh
 update-alternatives --list php # List available php versions
 sudo update-alternatives --config php # Set php cli version
 ```

### List files

```sh
ls -lh # lists files detailly with human readable format
ls -al # lists files detailly with hidden files
ls -l --block-size=M # List files with size in MB
```

### Certbot

```sh
# Issue new ssl cert for domain
sudo certbot -d mydomain.info --nginx

# Renew certtificates
sudo certbot renew
```