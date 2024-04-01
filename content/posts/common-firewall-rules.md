---
title: "Common Firewall Rules"
date: 2024-04-01T20:47:12+03:00
draft: false
tags: ['linux', 'security', 'firewall']
---


# List of common firewall linux

### 1. Allow SSH (port 22) from a specific IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="192.168.1.2" 
port protocol="tcp" port="22" accept' --permanent
sudo firewall-cmd --reload
```
### Block incoming ICMP (ping) requests:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" protocol value="icmp" drop' --
permanent
sudo firewall-cmd --reload
```

### Allow traffic from a specific network range:

```bash
sudo firewall-cmd --zone=public --add-source=192.168.0.0/24 --permanent
sudo firewall-cmd --reload
```

### Open a custom port range (e.g., 5000-6000):

```bash
sudo firewall-cmd --zone=public --add-port=5000-6000/tcp --permanent
sudo firewall-cmd --reload
```

### Block outgoing traffic on a specific port (e.g., 8080):

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" port protocol="tcp"
port="8080" drop' --permanent
sudo firewall-cmd --reload
```

### Allow FTP (port 21) for a specific interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" interface="eth0" port
protocol="tcp" port="21" accept' --permanent
sudo firewall-cmd --reload
```

### Block specific service (e.g., Telnet):

```bash
sudo firewall-cmd --zone=public --remove-service=telnet --permanent
sudo firewall-cmd --reload
```


### Allow multicast traffic:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="224.0.0.0/4"
drop' --permanent
sudo firewall-cmd --reload
```

### Allow specific application traffic (e.g., Apache):

```bash
sudo firewall-cmd --zone=public --add-service=http --permanent
sudo firewall-cmd --reload
```

### Block traffic from a specific country (e.g., Russia):

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="0.0.0.0/0"
invert source="country" destination country="RU" drop' --permanent
sudo firewall-cmd –reload
```

### Allow DNS (port 53) for both TCP and UDP:

```bash
sudo firewall-cmd --zone=public --add-port=53/tcp --add-port=53/udp --permanent
sudo firewall-cmd --reload
```

### Allow incoming traffic on a specific network interface (e.g., eth1):

```bash
sudo firewall-cmd --zone=public --add-interface=eth1 --permanent
sudo firewall-cmd --reload
```

### Block all incoming traffic except for established connections:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="0.0.0.0/0"
drop' --permanent
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="0.0.0.0/0"
accept' --permanent
sudo firewall-cmd --reload
```

### Allow only specific IP addresses on a certain port (e.g., 8080):

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" port protocol="tcp"
port="8080" source address="192.168.1.2" accept' --permanent
sudo firewall-cmd --reload
```

### Open port 123 for NTP (Network Time Protocol):

```bash
sudo firewall-cmd --zone=public --add-port=123/udp --permanent
sudo firewall-cmd --reload
```


### Allow ICMP echo requests (ping) from a specific subnet:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
address="192.168.0.0/24" protocol="icmp" accept' --permanent
sudo firewall-cmd --reload
```

### Block traffic to a specific IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="0.0.0.0/0"
destination address="192.168.1.2" drop' --permanent
sudo firewall-cmd --reload
```

### Allow SSH on a non-default port (e.g., 2222):

```bash
sudo firewall-cmd --zone=public --add-port=2222/tcp --permanent
sudo firewall-cmd --reload
```

### Allow traffic based on a custom service:

```bash
sudo firewall-cmd --zone=public --add-service=my_custom_service --permanent
sudo firewall-cmd --reload
```

### Block all incoming and outgoing traffic:

```bash
sudo firewall-cmd --zone=public --set-target=DROP --permanent
sudo firewall-cmd --reload
```

### Allow RDP (Remote Desktop Protocol - port 3389) from a specific IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="192.168.1.2"
port protocol="tcp" port="3389" accept' --permanent
sudo firewall-cmd --reload
```


### Allow traffic for a specific application (e.g., PostgreSQL):

```bash
sudo firewall-cmd --zone=public --add-service=postgresql --permanent
sudo firewall-cmd --reload
```


### Allow incoming connections on a specific port range (e.g., 8000-9000) for UDP:

```bash
sudo firewall-cmd --zone=public --add-port=8000-9000/udp --permanent
sudo firewall-cmd --reload
```


### Allow SIP (Session Initiation Protocol - port 5060) for VoIP:

```bash
sudo firewall-cmd --zone=public --add-port=5060/udp --permanent
sudo firewall-cmd --reload
```


### Block specific MAC address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
mac="00:11:22:33:44:55" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic for a specific user:

```bash
sudo firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -m owner --uid-owner username -j
ACCEPT
sudo firewall-cmd --reload
```

### Allow NFS (Network File System - port 2049) for file sharing:

```bash
sudo firewall-cmd --zone=public --add-port=2049/tcp --permanent
sudo firewall-cmd --reload
```

### Allow Docker containers to communicate on a bridge network:

```bash
sudo firewall-cmd --zone=trusted --add-source=172.17.0.0/16 --permanent
sudo firewall-cmd --reload
```

### Block outgoing traffic to a specific IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" destination
address="203.0.113.10" drop' --permanent
sudo firewall-cmd --reload
```

### Allow SNMP (Simple Network Management Protocol - port 161) for monitoring:

```bash
sudo firewall-cmd --zone=public --add-port=161/udp --permanent
sudo firewall-cmd --reload
```

### Allow incoming traffic on a specific port for IPv6 (e.g., port 8080):

```bash
sudo firewall-cmd --zone=public --add-port=8080/tcp --permanent --ipv
sudo firewall-cmd --reload
```


### Block all traffic except for a specific service (e.g., SSH):

```bash
sudo firewall-cmd --zone=public --add-service=ssh --permanent
sudo firewall-cmd --zone=public --remove-service={http,https} --permanent
sudo firewall-cmd --reload
```

### Allow traffic from and to a specific network interface (e.g., eth0):

```bash
sudo firewall-cmd --zone=public --add-interface=eth0 --permanent
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source interface="eth0"
accept' --permanent
sudo firewall-cmd --reload
```

### Allow DNS traffic only for a specific domain:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="0.0.0.0/0"
destination domain="example.com" accept' --permanent
sudo firewall-cmd --reload
```

### Block traffic from a specific country for a specific service (e.g., SSH):

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="0.0.0.0/0"
invert source="country" destination port="22" protocol="tcp" drop' --permanent
sudo firewall-cmd --reload
```

### Allow multicast traffic for IPv6:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv6" source address="fe80::/10"
drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic for a specific UDP service (e.g., syslog - port 514):

```bash
sudo firewall-cmd --zone=public --add-port=514/udp --permanent
sudo firewall-cmd --reload
```

### Allow traffic from a specific MAC address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
mac="00:11:22:33:44:55" accept' --permanent
sudo firewall-cmd --reload
```

### Allow outgoing SMTP traffic (port 25) for a specific IP range:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
address="192.168.1.0/24" port protocol="tcp" port="25" accept' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a custom port range for both TCP and UDP (e.g., 7000-8000):

```bash
sudo firewall-cmd --zone=public --add-port=7000-8000/tcp --add-port=7000-8000/udp --
permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for both TCP and UDP, limiting it to a specific IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="192.168.1.2"
port port="8000-9000" protocol="tcp" accept' --permanent
sudo firewall-cmd --reload
```

### Block traffic to a specific port from a range of IP addresses:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
address="192.168.0.0/24" port port="1234" protocol="tcp" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic for a specific user on a custom port:

```bash
sudo firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -m owner --uid-owner username -p tcp --
dport 9876 -j ACCEPT
sudo firewall-cmd --reload
```

### Block outgoing traffic to a specific domain:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" destination
domain="example.com" drop' --permanent
sudo firewall-cmd --reload
```

### Allow NTP traffic (port 123) for both TCP and UDP:

```bash
sudo firewall-cmd --zone=public --add-port=123/tcp --add-port=123/udp --permanent
sudo firewall-cmd --reload
```

### Allow traffic from a specific country on a specific port (e.g., 8080):

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="0.0.0.0/0"
source country="US" port port="8080" protocol="tcp" accept' --permanent
sudo firewall-cmd --reload
```

### Allow traffic for a specific service on a custom interface (e.g., eth1):

```bash
sudo firewall-cmd --zone=public --add-service=http --add-interface=eth1 --permanent
sudo firewall-cmd --reload
```

### Allow incoming and outgoing traffic on a specific port only for a specific time:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" port port="9876"
protocol="tcp" accept' --permanent --active-from=Mon-Fri 08:00-17:
sudo firewall-cmd --reload
```

### Allow traffic for a specific service from a specific IP address range:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
address="192.168.0.0/24" service name="ftp" accept' --permanent
sudo firewall-cmd --reload
```

### Allow traffic from and to a specific port for a range of IP addresses:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
address="192.168.0.0/24" port port="5432" protocol="tcp" accept' --permanent
sudo firewall-cmd –-reload
```

### Allow traffic on a specific port range for both TCP and UDP, limiting it to a specific MAC address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
mac="00:11:22:33:44:55" port port="8000-9000" protocol="tcp" accept' --permanent
sudo firewall-cmd --reload
```

### Block traffic from a specific user on a custom port:

```bash
sudo firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -m owner --uid-owner username -p tcp --
dport 9876 -j DROP
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range from a specific country:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source country="US" port
port="8000-9000" protocol="tcp" accept' --permanent
sudo firewall-cmd --reload
```

### Block traffic to a specific domain for a specific service (e.g., SSH):

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" destination
domain="example.com" service name="ssh" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a custom port range for a specific service (e.g., SNMP):

```bash
sudo firewall-cmd --zone=public --add-service=snmp --add-port=6000-7000/tcp --permanent
sudo firewall-cmd --reload
```

### Allow traffic for a specific user and specific service:

```bash
sudo firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -m owner --uid-owner username -p tcp --
dport 1234 -j ACCEPT
sudo firewall-cmd --reload
```

### Block ICMP echo requests (ping) from a specific IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="192.168.1.2"
protocol="icmp" icmp-type="8" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent
sudo firewall-cmd --reload
```

### Block traffic from a specific IP address range on a specific port:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
address="192.168.0.0/24" port port="9876" protocol="tcp" drop' --permanent
sudo firewall-cmd --reload
```

### Allow incoming traffic on a specific port for both TCP and UDP, limiting it to a specific user:

```bash
sudo firewall-cmd --direct --add-rule ipv4 filter INPUT 0 -m owner --uid-owner username -p tcp --
dport 8080 -j ACCEPT
sudo firewall-cmd --direct --add-rule ipv4 filter INPUT 0 -m owner --uid-owner username -p udp --
dport 8080 -j ACCEPT
sudo firewall-cmd --reload
```


### Allow traffic on a specific port for a range of IP addresses during specific days and times:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="192.168.1.10-
192.168.1.20" port port="8080" protocol="tcp" accept' --permanent --active-
on=Mon,Tue,Wed,Thu,Fri --active-at="08:00-17:00"
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for both TCP and UDP, limiting it to a specific user and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source address="192.168.1.2"
port port="8000-9000" protocol="tcp" accept' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Block traffic from a specific MAC address for a specific service:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
mac="00:11:22:33:44:55" service name="ftp" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a custom port range for a specific application and user:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -j ACCEPT
sudo firewall-cmd --reload
```

### Block incoming and outgoing traffic on a specific port for a specific user:

```bash
sudo firewall-cmd --direct --add-rule ipv4 filter INPUT 0 -m owner --uid-owner username -p tcp --
dport 9876 -j DROP
sudo firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -m owner --uid-owner username -p tcp --
dport 9876 -j DROP
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service and network interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" accept' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="ssh" port
port="2222" protocol="tcp" source address="192.168.1.2" accept' --permanent
sudo firewall-cmd --reload
```

### Block traffic from a specific country on a specific port for a specific service:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source country="CN" port
port="80" protocol="tcp" service name="http" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application and destination IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" destination address="192.168.1.2" accept' --permanent
sudo firewall-cmd --reload
```

### Block traffic from a specific MAC address for a specific service and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source
mac="00:11:22:33:44:55" service name="ftp" drop' --permanent --interface=eth
sudo firewall-cmd –-reload
```

### Allow traffic on a specific port range for a specific application, user, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -o eth1 -j ACCEPT
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific country:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" source country="RU" port
port="3000-4000" protocol="tcp" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service, source IP address, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source address="192.168.1.2" accept' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application, user, and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -s 192.168.1.2 -j ACCEPT
sudo firewall-cmd --reload
```

### Block traffic on a specific port for a specific service and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source address="192.168.1.2" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application, user, and destination IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -d 192.168.1.2 -j ACCEPT
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service, source MAC address, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source mac="00:11:22:33:44:55" accept' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service, source MAC address, and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source mac="00:11:22:33:44:55" source address="192.168.1.2"
accept' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application, user, source IP address, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -s 192.168.1.2 -o eth1 -j ACCEPT
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application, user, source IP address, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -s 192.168.1.2 -o eth1 -j ACCEPT
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" source address="192.168.1.2" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service, source MAC address, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source mac="00:11:22:33:44:55" accept' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application and destination IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" destination address="192.168.1.2" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application, user, and destination IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -d 192.168.1.2 -j ACCEPT
sudo firewall-cmd --reload
```
### Allow traffic on a specific port for a specific service, source MAC address, and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source mac="00:11:22:33:44:55" source address="192.168.1.2"
accept' --permanent
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" drop' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service, source IP address, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source address="192.168.1.2" accept' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application, user, and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" source address="192.168.1.2" drop' --permanent --direct --
add-rule ipv4 filter OUTPUT 0 -m owner --uid-owner username -s 192.168.1.2 -j DROP
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application, user, and destination IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -d 192.168.1.2 -j ACCEPT
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application, user, and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -s 192.168.1.2 -j ACCEPT
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" source address="192.168.1.2" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service, source MAC address, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source mac="00:11:22:33:44:55" accept' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application and destination IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" destination address="192.168.1.2" drop' --permanent
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service, source MAC address, and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source mac="00:11:22:33:44:55" source address="192.168.1.2"
accept' --permanent
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" drop' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Allow traffic on a specific port for a specific service, source IP address, and interface:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" service name="http" port
port="8080" protocol="tcp" source address="192.168.1.2" accept' --permanent --interface=eth
sudo firewall-cmd --reload
```

### Block incoming traffic on a specific port range for a specific application, user, and source IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" source address="192.168.1.2" drop' --permanent --direct --
add-rule ipv4 filter OUTPUT 0 -m owner --uid-owner username -s 192.168.1.2 -j DROP
sudo firewall-cmd --reload
```

### Allow traffic on a specific port range for a specific application, user, and destination IP address:

```bash
sudo firewall-cmd --zone=public --add-rich-rule='rule family="ipv4" application="my_custom_app"
port port="8000-9000" protocol="tcp" accept' --permanent --direct --add-rule ipv4 filter OUTPUT 0

- m owner --uid-owner username -d 192.168.1.2 -j ACCEPT
sudo firewall-cmd --reload
```

### Block incoming and outgoing traffic on a specific port for a specific user:

```bash
bash sudo firewall-cmd --direct --add-rule ipv4 filter INPUT 0 -m owner --uid-owner username -p
tcp --dport 9876 - j DROP sudo firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -m owner --
uid-owner username -p tcp --dport 9876 -j DROP sudo firewall-cmd --reload
```

