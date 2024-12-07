On the searchimg page located at the following address: http://<IP_ADDRESS>/?page=searchimg, there is an image search form.

When you enter any line into the form, an SQL error is displayed. Therefore, we assume that we can perform an SQL injection to potentially find a new flag.

After testing the simplest SQL injection: 1 or 1 = 1, we received confirmation that the form is vulnerable to SQL injections :

1 or 1 = 1

Based on this, we decided to try to display various tables in the database and their corresponding columns.
After some research, we found the following way to display many columns from the database, including the list_images table :

1 or 1=1 UNION SELECT table_name, column_name FROM information_schema.columns


From here, we started displaying the contents of each column of the users table in pairs: id, url, title, comment.
While displaying the contents of the URL and the comment, we came across information regarding the flag.

Then we displayed the contents of each column of the list_images table in pairs: id, url, title and comment.
When we displayed the contents of the url and comment columns, we found information about the new flag:

1 or 1=1 UNION select url, comment from list_images

So we decrypted 1928e8083cf461a5130363093573c46 using md5decrypt and got the string albatroz.

According to the instructions, we then converted the string to lowercase and encrypted it with SHA256 to get the flag.