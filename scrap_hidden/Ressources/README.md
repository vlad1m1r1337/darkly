At first, we wondered if the web application had any existing/hidden files that were not accessible through the main pages of the website. 
After manually going through various common URL combinations, we decided to look for applications that could do the job for us. 
After some research, we found Drb: a web content scanner that searches for existing (and/or hidden) web objects. 
It basically works by launching a dictionary-based attack against a web server and analyzing the responses.

Dirb has displayed several existing/hidden files, including the file .hidden http://127.0.0.1/.hidden/
The specified page contains an index page with several directories and subdirectories, all of which lead to several files README.md
We have come to the conclusion that we will have to look through all the different directories and subdirectories to analyze each file README.md and thus find the flag.