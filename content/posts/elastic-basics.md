---
title: "Elasticsearch and Kibana paths"
date: 2022-06-03T22:34:23+03:00
---

Start/stop/restart:
```
sudo systemctl restart elasticsearch.service
sudo systemctl restart kibana.service
```

Config folders:
```
/etc/elasticsearch/
/etc/kibana/
```

Certicate files for the api clients:
```
/etc/elasticsearch/certs/
```

ES Scripts for enrollment tokes and certicates generation:
```
/usr/share/elasticsearch/bin/
/usr/share/kibana/bin/
```