As you know, each nginx server stores a configuration file named "/etc/passwd" located at http://<IP_ADDRESS>?page=/etc/passwd in this case. 
Our idea was to get the contents of this popup on the server by going through the directories and searching until we get another popup other than the one shown above. 
We created this exploit.js
The script exploits a directory traversal vulnerability on the web server by sequentially traversing directories, accessing files such as "/etc/passwd", and searching for HTML script tags containing the keyword "flag" to potentially extract confidential information.
The exploit displayed a flag.