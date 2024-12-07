Instagram Facebook has links to popular social media platforms such as Facebook, Twitter and Instagram. 
However, the vulnerability allows users to change the "site" parameter in these links, which leads to a specific URL structure ( http://<IP_ADDRESS>/index.php?page=redirect&site={string} ).

Using this problem and replacing the site element in the HTML anchor tag with any string (a valid URL, an empty or random string, etc.), a flag is displayed on the redirected page.
This type of vulnerability is known as open redirection, which allows attackers to redirect users from a legitimate website to any arbitrary URL, potentially leading them to malicious sites. 
To minimize this risk, it is necessary to implement appropriate input verification and secure redirection methods to prevent unauthorized redirects and protect users from potential attacks.