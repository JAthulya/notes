php reverseshell = https://github.com/pentestmonkey/php-reverse-shell/blob/master/php-reverse-shell.php

__GET A BETTER SHELL__
python -c "import pty; pty.spawn('/bin/bash')"

__find setuid__
cat /
find / -perm /4000

__find setguid__
find / -perm /2000

__CHECK RUNNING PROCESS__
ps aux

__PRIVILEDGE ESCALATION__
/bin/systemctf
go to GTFObins
edit the code and run it
bash -p
now we have root access



