We installed Hydra and executed the following command:
hydra -l admin -P ./Downloads/rockyou.txt -F <IP_ADDRESS> http-get-form '/index.php:page=signin&username=^USER^&password=^PASS^&Login=Login:F=images/WrongAnswer.gif'
Where:
-l admin : use admin as the username (we just assumed that admin would be a valid username).
-P ./Downloads/rockyou.txt -F : Try all the passwords listed in the dictionary of the most common passwords suggested in this guide and exit after the first login/password pair found for any host.
<IP_ADDRESS> : The IP address of our website.
http-get-form '/index.php:page=signin&username=^USER^&password=^PASS^&Login=Login:F=images/WrongAnswer.gif' :
We used http-get-form because it emulates sending a form, which distinguishes it from a standard HTTP request. 
We determine success by the lack of display "WrongAnswer.gif " on the URL "http://<IP_ADDRESS>/?page=signin&username=admin&password=shadow&Login=Login#".

We received a response that the correct password is shadow, logged in with admin/shadow and received a flag.

How to protect yourself from Hydra password matching:
A strong password
Change your password regularly
Account lockdown after several failed login attempts
Captcha