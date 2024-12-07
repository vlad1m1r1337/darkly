On the members page located at the following http URL://<IP_ADDRESS>/?page=member, there is a member search form by ID. 
When you enter any line into the form, an SQL error is displayed.

Therefore, we assume that we can perform an SQL injection to potentially find a new flag.

After testing the simplest SQL injection: 1 or 1 = 1, we received confirmation that the form is vulnerable to SQL injections:

1 or 1 = 1

Based on this, we decided to try to display various tables in the database and their corresponding columns. 
After some research, we found the following way to display many columns from the database, including the "users" table, as shown below:

1 or 1=1 UNION SELECT table_name, column_name FROM information_schema.columns

From that moment on, we started displaying the contents of each column of the users table in pairs: user_id, first_name, last_name, town, country, planet, Commentaire, countersign.
When displaying the content of Commentaire and countersign, as shown below, we came across information regarding the flag.

Then we displayed the contents of each column of the users table in pairs: user_id, first_name, last_name, town, country, planet, Commentaire and countersign.
When we displayed the contents of the Commentaire and countersign columns, we found information about the new flag:

1 or 1=1 UNION SELECT Commentaire, countersign FROM users

So we decrypted 5ff9d0165b4f92b14994e5c685cdce28 using md5decrypt and got the string FortyTwo.

According to the instructions, we then converted the string to lowercase and encrypted it with SHA256 to get the flag.