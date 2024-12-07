After the directory is found .hidden and its functions, we used the Dirb web content scanner to investigate further. 
Our scan revealed the existence of an htpasswd file located at http://<IP_ADDRESS>/whatever/htpasswd . 
By clicking on this URL, we uploaded the file .htpasswd containing important login credentials, including the root password, which we decrypted using md5decrypt.
In addition, our Dirb scan revealed a hidden administration page at http://<IP_ADDRESS>/admin . 
Armed with the decrypted credentials, we tried to access the administration page using the root username and the recovered password qwerty123@.
This successful login redirected us to a page containing a new flag.