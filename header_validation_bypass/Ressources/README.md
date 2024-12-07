While exploring the main page of the site, we found a new link in the footer leading to another section. 
On this new page located at http://<IP_ADDRESS>/?page=b7e44c7a40c5f80139f0a50f3650fb2bd8d00b0d24667c4c2ca32c88e13b758f ,
displays a brief description of the birds of the Diomedeid family, supplemented by an image of this bird.
These comments seem to refer to certain HTTP headers: referer and user agent :
The referer header identifies the URL of the previous web page from which the current request was received. 
In this case, it assumes that the request should come from https://www.nsa.gov / .
On the other hand, the user agent header identifies the software or browser used to make the request, and in this context it is recommended to use ft_bornToSe c**.

To do this, we executed the following command:
curl -s -A 'ft_bornToSec' --referer "https://www.nsa.gov/" "http://<IP_ADDRESS>/?page=b7e44c7a40c5f80139f0a50f3650fb2bd8d00b0d24667c4c2ca32c88e13b758f" | grep 'flag'
Where:
curl : a command-line tool for transferring data using URLs.
-s : Works in silent mode, displaying only output data.
-A 'ft_bornToSec' : Sets the user agent to ft_bornToSec .
-referer " https://www.nsa.gov / " : Sets the referrer to https://www.nsa.gov / .
"http://<IP_ADDRESS>/?page=b7e44c7a40c5f80139f0a50f3650fb2bd8d00b0d24667c4c2ca32c88e13b758f" : sends a request to this URL, where <IP_ADDRESS> should be replaced with the IP address of the vulnerable website.
grep 'flag' : Filters the output to display lines containing the flag.