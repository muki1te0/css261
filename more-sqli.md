As the name suggests we try to log in using sql injection. We can try username: admin (actually, it can be anything) and password: 1' OR 1=1;--
Then we proceed to welcome.php
Here we have Search Bar which also can be injected. Using in-band sql injection we can numerate through the database to try to find the name of it.
After we found out the name of database, which is 'SQLiLite', I have tried to leak some data using following query: 
' UNION SELECT name, sql, null from sqlite_master;--

Then after we found some text with a name flag, we try to leak it using: 
' UNION SELECT flag, null, null from more_table;--

That way we have obtained the flag, which is: picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8ee9477}	