+++
date = '2025-01-03T09:23:38+08:00'
draft = true
title = 'Cmd Notes'
+++

- **nslookup**: a network administration tool used to query Domain Name System (DNS) servers to obtain domain name or IP address mapping information.
```
% nslookup shuxiu-jia.github.io
Server:		26.26.26.53
Address:	26.26.26.53#53

Non-authoritative answer:
Name:	shuxiu-jia.github.io
Address: 185.199.111.153

```
---

- **ping**: a fundamental network diagnostic tool used to test connectivity between devices on a network.
```
% ping -c2 d2l.ai  
```
---

```
# Manually sending an HTTP request to the server 
% nc 93.184.215.14 80
GET / HTTP/1.1
Host: www.example.com
```
---
- **curl/wget**

---
- **hugo**:
```
hugo --baseURL="https://shuxiu-jia.github.io/"
```