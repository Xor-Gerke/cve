# Product Show Room Site - 'Telephone' Stored Cross-Site Scripting(XSS)

   
#### Exploit Title: Product Show Room Site - 'Telephone' Stored Cross-Site Scripting(XSS)
#### Exploit Author: webraybtl@webray.com.cn inc
#### Vendor Homepage: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html
#### Software Link: https://www.sourcecodester.com/download-code?nid=15370&title=Product+Show+Room+Site+in+PHP%2FOOP+Free+Source+Code
#### Version: Product Show Room Site 1.0
#### Tested on: Windows Server 2008 R2 Enterprise, Apache ,Mysql

#### Description
Persistent XSS (or Stored XSS) attack is one of the three major categories of XSS attacks, the others being Non-Persistent (or Reflected) XSS and DOM-based XSS. In general, XSS attacks are based on the victim’s trust in a legitimate, but vulnerable, website or web application.Product Show Room Site does not filter the content correctly at the "Contact info-Telephone" module, resulting in the generation of stored XSS.

#### Payload used:
`<script>alert(111)</script>`

#### Proof of Concept

1. Login the CMS. 
Default Admin Access
Username: admin
Password: admin123

1. Open Page http://172.24.5.107/psrs/admin/?page=system_info/contact_info and click View button

2. Put XSS payload  (`<script>alert(111)</script>`) in the Telephone box and click on Update to publish the page
   ![image](https://user-images.githubusercontent.com/60683449/171591851-2068eea2-b789-464f-8afb-9f6b6f8eaedd.png)
    
3. Open http://172.24.5.107/psrs/?p=contact,Viewing the successfully published page,We can see the alert.
   ![image](https://user-images.githubusercontent.com/60683449/171591881-2962a429-f2de-4979-8e27-6fdd8f62c61c.png)

